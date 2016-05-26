# Box Model and Positioning

## Objectives

- Describe the difference between inline, block, and inline-block display
- Adjust element spacing using padding and margin
- Float elements
- Explain static, relative, fixed, and absolute positioning
- Lay out pages and use z-index

## Display types

The `display` property controls how an element is placed and spaced on a page.

- `display: block` - Gives an element width, height, and its own space in the flow of the document
- `display: inline` - The element will render alongside other inline elements. The element stays within and the document flow.
- `display: inline-block` - Gives the element dimensions and the ability to position itself like a block element but will render like an inline element.

## Box model

- `padding` is the amount of space inside of an element (between the content of the element and its border)
- `margin` is the spacing outside of an element. Like an invisible field that stops other elements from getting within a certain distance of an element
- `border` counts toward the width of an element in the standard box model.

__PRO TIP:__ Set `box-sizing: border-box` on an element to have it render using Internet Explorer's box model which makes a lot more sense than the standard.

In the standard box model adding padding and/or borders to an element will increase its width. In the `border-box` (or IE) model padding and borders do no increase an element's width.

## Positioning

- `static` is the standard positioning every element gets. You never declare an element to have static positioning (unless you have a really good reason to which you won't - I haven't seen any reason in 8 years of professional front-end development)
- `relative` positioning allows you to move an element from it's initial position *relative* to where it would have been positioned originally using static positioning
- `fixed` positioning will glue the element to the browser window at the coordinates you set and will not move when scrolling
- `absolute` positioning is like `fixed` but the element won't stick to the screen when scrolling like `fixed` positioned elements
