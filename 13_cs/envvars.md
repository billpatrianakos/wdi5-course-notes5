# The Terminal Environment

Every computer or server you ever work with will have its own terminal environment. This environment is made up of all the processes the system is running as well as variables that change how those processes run.

## Setting Environment Variables (envvars)

There are *generally* two ways you'll be setting envvars (we'll be calling Environment Variables `envvars`  a lot through the rest of this sections).

### Option 1: Setting at runtime

To set an environment variable at program run time you'll want to simply set it when you run the command to open the program. Here are some examples for how you'd use this concept when starting a Ruby or Node.js web application either locally or on your own server.

__*Ruby - Setting `envvars` at runtime*__

```shell
RACK_ENV=production AUTH_SALT=h4JAig91jXeprIJ56lA4SIRX AUTH_KEY=iAWpGQ9HuaoSOgjNJ6XFLpzG AWS_BUCKET=my-bucket AWS_USER=my-aws-user AWS_SECRET_KEY="o+c//z+QP).UHsr\pFaTUKh5y:-M<q2.d$:NNj/Xl(ac@3B[{F%W4P5|9hXv{uQ\M]T?7Mo`!$rxyX{mZujC}zPW6@^_XHV2[{A9g:j2gbEd\V|jmO(.wR=Uy_Y@Ng&jqYyV0XBZa>:^bX\PbMCKjI9{.6vPUpyR?de2t1^:VqhL47I!w0K~CG/SOAZKhUZh7<nNdjPp@I8.&7r!#2QPd/%raa@S1X-*]1uY*d*cl8I[4m{5i<=[#(z3TD|DQ%%=" rackup ./config.ru
```

Holy sh*t. What the #%@! is that monstrosity of a shell command above? I'll tell you. It's what you need to do to set envvars at program runtime (a.k.a. when the program starts up and begins running). What this means is that when your program starts up it'll have the environment variables you set available to it rather than whatever the defaults were (if there were any defaults to begin with).

The alternative to this is hard coding secret data in your application then pushing it to a public git repository like maybe GitHub where you'll get laughed at *any* someone will gain access to your [Amazon Web Services](https://aws.amazon.com) accounts at the very least.

Another alternative would be to simply keep your secret variables in a separate file, ignore that file in your repository, then set those variables, once again, at runtime. This, again, is not a good solution at all. Once you get past three or four envvars it gets really awkward to have to manually start your application in this way.

A while back someone came up with an elegant solution to this problem called [dotenv](https://github.com/bkeepers/dotenv). At the time everyone rejoiced and there was finally a good, sensible way to keep your environment variables that are being used by open source programs hidden from your public repository. The idea was simple and it went like this:

1. Create a file called `.env`
2. Inside of `.env` you define your variable definitions (one per line in the same style as bash terminal or shell scripts: `NODE_ENV=production node ./app.js`)
3. You add your `.env` file to your `.gitignore` file then be sure to commit your `.gitignore` before any other file at that point.
4. In your application's startup script (let's take `config.ru` as an example) you require the library and then load the envvars. It looks like this in Ruby:

```ruby
require 'dotenv'
Dotenv.load

# my ruby code here...
```

*Note: dotenv was originally written for use with Ruby but there are now libraries for almost every programming language.*

You might now ask, how do I get my environment variables loaded on my production server if the `.env` file is being ignored by git? The answer is that you shouldn't be using `dotenv` or anything like it in production. Instead, use a proper deployment package like [Capistrano for Ruby](http://capistranorb.com) or [PM2 for Node.js](https://github.com/Unitech/pm2). These packages will have additional configuration files that you'll need to add to your `.gitignore` file and you'll be defining your envvars in these deployment packages' config files.

 Yes, you may be writing environment variables twice (once in the a separate file and once in the deploymeny config) but in the end they're the better way to deploy an application. `dotenv` is only for development environment use.

But all that aside, setting the envvars at program runtime is really ugly and gross looking isn't is? If only there were a better way. There is! In Node (and other languages), you can write your own code to load up environment variables from a separate files easily and more efficiently than dotenv. dotenv was a great idea for its time but now that we understand the concept, let's take it a step further and show you how to do exactly what `dotenv` does, except manually, in just a few lines of code.

## Option 2: Setting them from an executable file

This method of setting envvars requires you to create a shell script that sets some envvars and then run that script before starting your application. Here's how it works:

1. Create a new file to define your envvars (I call mine `envvars.sh`) and make it executable (example: `touch envvars.sh && chmod +x envvars.sh`)
2. Add this file to your `.gitignore` by running `echo "envvars.sh" >> .gitignore`
3. Be sure to add and commit your `.gitignore` file *before you do anything else at this point*. Go ahead. We'll wait till your finished before moving on...
4. Now you can start your application by running two commands: `source envvars.sh && npm start` (replace `npm start with whatever startup command you use in your project) 

The shell script we created in step 1 will look like this:

```shell
#!/bin/sh

export RACK_ENV=production
export AUTH_SALT=h4JAig91jXeprIJ56lA4SIRX
export AUTH_KEY=iAWpGQ9HuaoSOgjNJ6XFLpzG
export AWS_BUCKET=my-bucket
export AWS_USER=my-aws-user
export AWS_SECRET_KEY="o+c//z+QP).UHsr\pFaTUKh5y:-M<q2.d$:NNj/Xl(ac@3B[{F%W4P5|9hXv{uQ\M]T?7Mo`!$rxyX{mZujC}zPW6@^_XHV2[{A9g:j2gbEd\V|jmO(.wR=Uy_Y@Ng&jqYyV0XBZa>:^bX\PbMCKjI9{.6vPUpyR?de2t1^:VqhL47I!w0K~CG/SOAZKhUZh7<nNdjPp@I8.&7r!#2QPd/%raa@S1X-*]1uY*d*cl8I[4m{5i<=[#(z3TD|DQ%%="

echo "Environment variables set" # We echo these out to ensure the script ran
echo $RACK_ENV
echo $AUTH_SALT
echo $AUTH_KEY
echo $AWS_BUCKET
echo $AWS_USER
echo $AWS_SECRET_KEY
```

Now to run your application in dev mode you run `source envvars.sh && gulp` or `source envvars.sh && npm start`. The second command can be customized for whichever language you're using so we can replace those `gulp` and `npm start` commands with `rackup` or something similar.

You only need to `source envvars.sh` once per terminal session. This means that if you've run `source envvars.sh` once in your current terminal window or tab you can stop and restart your application as many times as you want with no need to `source` your envvars file. This makes it possible to use tools like [rerun](https://github.com/alexch/rerun), [livereload](https://github.com/napcs/node-livereload), [nodemon](https://github.com/remy/nodemon), or any other startup command.

## Option 3: Programmatically set envvars

Unfortunately, this is an unreliable method and we'll be updating this section when we work out the kinks. Even though this option doesn't always work, I think that it's a clever idea and something worth showing you. Here's how it works:

*If you use gulp to run tasks like watching files and running servers this will work for you. If you use something else you'll need to figure out how to adapt this to your specific tooling.*

1. Create a shell script that looks exactly like the one in option 2 and make it executable as well
2. Create a gulp task that'll run some shell commands
3. Add the task to your default gulp task (should be the very first one in the list)

```js
// In gulpfile.js

const exec = require('child_process').exec;

gulp.task('setvars', function() {
  exec('source ./envvars.sh', function(err, stdout, stderr) {
    if (err) {
      console.log(err);
    } else if (stderr) {
      console.log(stderr);
    } else {
      console.log(stdout);
    }
  })
});

//... more tasks defined here ...//

gulp.task('default', ['setvars', 'watch', 'server']);
```

The way this works is we create a new process in Node - a child process - that executes a shell command in your environment. So if you use gulp as your task runner you can simply run gulp and as long as your default task is set up to run these tasks in this order:

1. `setvars` - the task that'll set environment variables by running the equivalent of you manually running `source envvars.sh`
2. `watch` - you want your watch method to come next so that it can read your entire project file structure and set up listeners
3. `server` - if you're running an Express app or even a static site you'll likely want to run this task last as it is a long running process and could prevent the other tasks in the list from running at all.

__*WARNING: This method is not reliable so don't use it for anything important. That said, isn't it pretty clever?*__

## Side notes

### What is `source`?

To `source` a file means to read it and apply and commands, settings, or exported variables in the current terminal session. When you run a shell script that exports (sets) environment variables those variables are only set or exist for as long as the program runs. However when you `source` a file, those settings stick to the current terminal session until you close that particular terminal window or tab.
