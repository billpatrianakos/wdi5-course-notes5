## Equation for Converting Pixels to EMs

The `em` is a measure of the height of one `m` character on the screen. The height of one letter `m` will always be different based on the font family and the default font size applied to the body of the page.

For example, if we use Arial at size 12px and measure the height of the `m` character we'll see it is 10px tall (that's not really true but we'll say it is for this example). Based on that we know that `1em` is equal to `10px`. 

When you use ems as your unit of measure you're multiplying the size of a lower case `m` times whatever number you add in front of it.

So if we continue on with our previous example then:

* `1em == 10px`
* `2em == 20px`
* `target / context = result` (Target = target font size, context = font size of containing element)

#### Example

Here is an `h1` using pixels:

```css
h1 {
  font-size: 30px;
  font-weight: bold;
}
```

We can convert that `px` value to `em`s:

`30px / 10px (standard font size) = 3em`

**Result:**

```css
h1 {
  font-size: 3em; /* 30x/10px */
  font-weight: bold;
}
```
