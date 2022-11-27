Before you get too far into your styling, you should make use of the `sr-only` class. You can use CSS to make elements with this class completely hidden from the visual page, but still be announced by screen readers.

The CSS you are about to write is a common set of properties used to ensure elements are completely hidden visually.

The `span[class~="sr-only"]` selector will select any `span` element whose `class` _includes_ `sr-only`. Create that selector, and give it a `border` property set to `0`.


The CSS `clip` property is used to define the visible portions of an element. Set the `span[class~="sr-only"]` selector to have a `clip` property of `rect(1px, 1px, 1px, 1px)`.

The `clip-path` property determines the shape the `clip` property should take. Set both the `clip-path` and `-webkit-clip-path` properties to the value of `inset(50%)`, forming the clip-path into a rectangle within the element.

Now you need to size these elements down. Give your `span[class~="sr-only"]` selector a `width` and `height` property set to `1px`.

To prevent the text content from overflowing, give your `span[class~="sr-only"]` selector an `overflow` property set to `hidden` and a `white-space` property set to `nowrap`.

Finally, you need to take these hidden elements out of the document flow. Give the `span[class~="sr-only"]` selector a `position` property set to `absolute`, a `padding` property set to `0`, and a `margin` property set to `-1px`. This will ensure that not only are they no longer visible, but they are not even within the page view.

```css
span[class~="sr-only"] {
	border: 0;
	clip: rect(1px, 1px, 1px, 1px);
	clip-path: inset(50%);
	-webkit-clip-path: inset(50%);
	height: 1px;
	width: 1px;
	position: absolute;
	overflow: hidden;
	white-space: nowrap;
	padding: 0;
	margin: -1px;
}
```
