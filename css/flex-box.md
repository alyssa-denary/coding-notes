#refactor 

Flexbox is a one-dimensional CSS layout that can control the way items are spaced out and aligned within a container.

To use it, give an element a `display` property of `flex`. This will make the element a _flex container_. Any direct children of a flex container are called _flex items_.

Flexbox has a main and cross axis. The main axis is defined by the `flex-direction` property, which has four possible values:

-   `row` (default): horizontal axis with flex items from left to right
-   `row-reverse`: horizontal axis with flex items from right to left
-   `column`: vertical axis with flex items from top to bottom
-   `column-reverse`: vertical axis with flex items from bottom to top

**Note**: The axes and directions will be different depending on the text direction. The values shown are for a left-to-right text direction.

Try the different values to see how they affect the layout.

The `flex-wrap` property determines how your flex items behave when the flex container is too small. Setting it to `wrap` will allow the items to wrap to the next row or column. `nowrap` (default) will prevent your items from wrapping and shrink them if needed.

The `justify-content` property determines how the items inside a flex container are positioned along the main axis, affecting their position and the space around them.
- flex-start
- center
- space-around
- space-between
- space-evenly
- flex-end

The `align-items` property positions the flex content along the cross axis. In this case, with your `flex-direction` set to `row`, your cross axis would be vertical.

Notice how some of your images have become distorted. This is because the images have different aspect ratios. Rather than setting each aspect ratio individually, you can use the `object-fit` property to determine how images should behave.
	-object-fit: cover;
		#add 

The `gap` CSS shorthand property sets the gaps, also knowns as gutters, between rows and columns. The `gap` property and its `row-gap` and `column-gap` sub-properties provide this functionality for flex, grid, and multi-column layout. You apply the property to the container element.

The `::after` pseudo-element creates an element that is the last child of the selected element. You can use it to add an empty element after the last image. If you give it the same `width` as the images it will push the last image to the left when the gallery is in a two-column layout. Right now, it is in the center because you set `justify-content: center` on the flex container.

Example:

```css
.container::after {
  content: "";
  width: 860px;
}
```





## Breakpoints
- Three major ways to choose breakpoints
	- Bad: Choosing ipad/iphone (or any specific device) widths to determine breakpoints
	- Good: Use most used devices widths to determine breakpoints
		- Can look up this data on StatCounter
	- Perfect: Ignore devices altogether and only worry about your content and design. Put breakpoints wherever your design starts to look weird. 
