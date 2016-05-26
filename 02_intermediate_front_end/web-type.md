# Web Typography

## Objectives

- Describe the difference between web fonts and desktop fonts
- Be able to use and apply web fonts to HTML pages
- Understand the fundamentals of good typesetting on the web

## Web Fonts vs. Desktop Fonts

Every computer comes with a collection of fonts installed by default. On the leading platforms like Windows, OS X, and Linux this list is predictable and mostly static. When you design a web site you may want to design it with a particular font in mind like Helvetica for example. But you have to remember that Helvetica is only installed as part of the default font sets on Mac OS X. Because of this you have to be sure to include one or more fallback fonts for users on a system that does not have your chosen font installed.

Often you'll want to use a font in your designs that users of any operating system and browser combination can render. In these cases you'll want to use a web font. A web font is a font file that is hosted online and downloaded along with your web page when required.

When a user loads a page that uses a desktop font as it's `font-family` the font is loaded from the user's system and then displayed. When a user loads a page that uses web fonts, the chosen font must be downloaded before the user's browser can render it properly.

## The `font-family` property

In CSS we use the `font-family` property to declare which fonts to use. The value of this property is declared as a list of fonts where the first font listed is the preferred font.

```css
p {
  font-family: Helvetica, Verdana, Arial, sans-serif;
}
```

### Using fallbacks

In all cases, regardless of whether you're using web fonts or desktop fonts, you need to define a set of fallback fonts in your `font-family` CSS rule. By defining fallbacks, if a user doesn't have your preferred font installed the browser will go through the list until it sees a font that is available on the system.

In the case of web fonts there are still cases where fallback fonts are important. A user's connection to your website may be prematurely ended before your web font can download. In cases like these a fallback font must be used. There may be incompatibilities between the web font file itself and the user's system that force the browser to use a fallback font as well.

There are a variety of reasons that your primary font may not be available (regardless of whether you're using web fonts or desktop fonts) so always use a fallback.

The last font listed in your `font-family` rule should be the type of font to use, not a name. For example, Helvetica is considered a sans-serif font. Serif fonts (like Times New Roman) have flourishes and decorations on the letterforms while sans-serif fonts (like Arial and Helvetica) are simple and don't have those flourishes.

- Use `serif` as the final fallback for serif style fonts (Times New Roman, etc.)
- Use `sans-serif` as the final fallback for sans-serif fonts (Helvetica, Arial, Verdana, Open Sans, etc.)
- Use `monospace` as the final fallback for monospace fonts (these are fixed-width fonts like the ones you use to write code in your favorite text editor)

## Web Fonts

Web fonts are used for two main reasons:

1. You can't ask your users to download your preferred font - that's annoying and no one will do it just to see your design
2. Many fonts that aren't system fonts have licensing issues that require users to pay for the font

Web fonts are often times licensed in such a way that users would need to pay to view the font on your website. The solution that developers and font foundries settled on is a system where users download web fonts in a "read-only" sort of way and the owner of the website pays for the users to be able to load the font. This way users don't have to install new fonts, designers get to use their favorite fonts, and font licenses are adhered to.

Many web fonts are open sourced but are still loaded in a "read-only" manner. [Google Web Fonts](https://www.google.com/fonts) is a place where you can browse and choose from a variety of fonts that will load on any computer to use in your designs.

### Using web fonts

There are two main ways to use web fonts.

#### 1. The easy way

Many font providers like Google Web Fonts and Typekit will give you a snippet of JavaScript or link to a CSS file that'll automatically load the fonts needed for your page. You just need to copy and paste the code they give you then simply set the `font-family` property on whichever elements you choose.

#### 2. The custom way

You may have a set of font files of your own that aren't available on any font services or you might just want to host a web font yourself. In these cases you must use the `@font-face` CSS property to load the font files you want your users to have access to.

```css
@font-face {
    font-family: 'League Spartan';
    src: url('leaguespartan-bold.eot');
    src: url('leaguespartan-bold.eot?#iefix') format('embedded-opentype'),
         url('leaguespartan-bold.woff2') format('woff2'),
         url('leaguespartan-bold.woff') format('woff'),
         url('leaguespartan-bold.ttf') format('truetype'),
         url('leaguespartan-bold.svg#league_spartanbold') format('svg');
    font-weight: bold;
    font-style: normal;
}

h1 { font-family:"League Spartan"; }
```

You can get web fonts from:

- **[MyFonts](http://www.myfonts.com/)** is a great marketplace for type designers to sell their stuff, so you see a wide variety of prices, from free to super expensive. They're good at organizing, and make it obvious & searchable to find fonts you can use on the web.
- **[Typekit](https://typekit.com/)**, which was recently bought by Adobe, is a subscription service that provides a library of awesome typefaces for use on the web.

- **[FontSquirrel](http://www.fontsquirrel.com/)** is a great list of free fonts – some open-source, some just free. They've also got a webfont generator, where you can upload a font (assuming you're legally allowed to use it), and they'll convert it to all the formats you need and give you a ready-to-use kit.
- **[Google Fonts](https://google.com/fonts)** is a large collection of free fonts, some open-source, which they host and let you reference. It's very easy to use and include if you want your fonts hosted somewhere.

- **[The League of Moveable Type](https://www.theleagueofmoveabletype.com/)**, is the first open-source type foundry, whose fonts are not only free to use, but free to dissect and learn from, too.
