## Position Property
Typically, HTML is rendered in a top-down manner. Elements at the top of the code are positioned at the top of the page. However, many times you may want to move the elements to different positions. You can do this with the `position` property.
```css
.selector {
	position: fixed;
	top: 0;
}
```
- Fixes selected item to top of viewport

```css
.selector {
	position: sticky;
	top: 0;
}
```

```css
.selector {
	position: relative;
}
```

```css
.selector {
	position: absolute;
	top: -2.25rem;
	left: 0.5rem;
}
```
- An `absolute` position takes the element out of that top-down document flow and allows you to adjust it relative to its container.

Other resource for understanding: https://css-tricks.com/almanac/properties/p/position/

## z-index
The `z-index` property is used to create "layers" for your HTML elements. If you are familiar with image editing tools, you may have worked with layers before. This is a similar concept.

Elements with a higher `z-index` value will appear to be layered on top of elements with a lower `z-index` value. This can be combined with the positioning in the previous lesson to create unique effects.

## Calc function
#refactor 
The `calc()` function is a CSS function that allows you to calculate a value based on other values. For example, you can use it to calculate the width of the viewport minus the margin of an element:

```css
.example {
  margin: 10px;
  width: calc(100% - 20px);
}
```

Ensure your years do not get hidden by setting a `z-index` of `999`. Then, give it a `margin` of `0 -2px`, and a `padding` set to `0.5rem calc(1.25rem + 2px) 0.5rem 0`.