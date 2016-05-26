# Responsive CSS

Responsive CSS is a way to style websites so they'll render optimally on any device no matter the screen size.

## Objectives

- Discern the difference between fluid and responsive design
- Know how to make CSS responsive
- What is mobile first

## Fluid design

In fluid design a page is styled using using a fluid grid. A fluid grid uses percentages rather than fixed pixel widths or other units. As the browser window grows and shrinks the design changes to fit the window area.

## Responsive design

At a certain point fluid designs begin to break down and look bad. They may squish to fill the available screen space but the content gets too mashed together and a whole new layout is required.

To remedy this situation we have a new feature in CSS3 called Media Queries. Media Queries allow you to ask the browser how much viewable space it has vertically and horizontally and apply special styles to it based on those measurements.

### Example

An example of this is easy. Load just about any website in a browser. Then change the browser window size to the point where its really small. Then pull out your phone and visit that same site on your phone. You'll notice the changes and differences. That's responsive web design. Most sites do it right. Hopefully you don't choose some weird site that's doing it wrong.

Responsive CSS with media queries is available in CSS3 but the great news is that it is __very__ widely supported and you should have no need to worry about browser support for media queries.

## Meta viewport setting

If you're designing a responsive website then you must be sure to include a meta tag in the `<head`> of your HTML page that defines the viewport. This will make it so that users on mobile devices won't load the page all weird and zoomed in when they first browse to your site. Include this code in your `<head>` tag of your HTML pages:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

__Resources:__

- [More information about the viewport meta tag here](https://css-tricks.com/snippets/html/responsive-meta-tag/)
- [Examples of badly set viewport meta tag (pay attention mostly to the images)](https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag)


## Media Queries

Media queries are CSS code you load *last* in your CSS files. They can target a type of screen, device, or even paper (for printing) and they can also target mininum and maximum screen sizes (at the same time). Here's an example:

```css
@media only screen and (max-width: 1023px) {

  body {
    font-size: 0.8em;
    line-height: 1.5em;
  }

}

@media handheld, only screen and (max-device-width: 450px) {
  .mobile-show { display: inline-block; }

  // Grid styling
  body, .container, .row, .row-loose {
    font-size: 1.1rem;
    width: 100%;
    min-width: 0;
    margin-left: 0;
    margin-right: 0;
    padding-left: 0;
    padding-right: 0;
  }

  .col-1,
  .col-1,
  .col-3,
  .col-4,
  .col-5,
  .col-6,
  .col-7,
  .col-8,
  .col-9,
  .col-10,
  .col-11,
  .col-12 {
    width: 100%;
  }
}
```

In the above example we're  making the font size and line height slightly smaller for when browser windows are less than the desired 1140px (which is what the grid this code came from specified). Then we target handheld devices only (like phones and tablets) and set the entire grid so everything stacks on top of each other. This is deal for mobile devices. We could get more specific and target as many devices as we wanted to but in this case we just target "screens slightly smaller than our ideal" and "any mobile device screen".

## Mobile First

Mobile first is the idea that you design for mobile devices first, creating a design meant for small screens, then expand your design physically from there.

There are [others who](http://www.html5rocks.com/en/mobile/responsivedesign/) can [explain it better than me](https://abookapart.com/products/mobile-first).

## Activity / Lab / Practice

Make your personal profile page (your GitHub pages page) responsive! This isn't homework, it's practice.

## RESOURCES

- [Responsive ("viewport") meta tag info](https://css-tricks.com/snippets/html/responsive-meta-tag/)
- [Media Query examples for standard and popular devices](https://css-tricks.com/snippets/css/media-queries-for-standard-devices/)
- [The MDN explanation of media query syntax](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [Web development boilerplate that incorporates all responsive best practices](https://github.com/billpatrianakos/fractionless-boilerplate/tree/master/src)
