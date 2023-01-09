- Flexbox is a one-dimensional CSS layout that can control the way items are spaced out and aligned within a container.
	- For two-dimensional layouts, see [[grid]]
- Main idea of flexbox: gives container ability to expand and shrink elements to best use available space. (replaces float layouts)

#refactor
## Using Flexbox
- To use it, give an element a `display` property of `flex`. This will make the element a _flex container_. Any direct children of a flex container are called _flex items_.
- Flexbox has a main and cross axis.
	- **Note**: The axes and directions will be different depending on the text direction. The values shown are for a left-to-right text direction.
![[flex-box-1673294090012.jpeg]]
### Container Properties
#### `flex-direction` 
- defines the main axis, and has four possible values:
	-   `row` (default): horizontal axis with flex items from left to right
	-   `row-reverse`: horizontal axis with flex items from right to left
	-   `column`: vertical axis with flex items from top to bottom
	-   `column-reverse`: vertical axis with flex items from bottom to top
#### `flex-wrap` 
- determines how your flex items behave when the flex container is too small. Setting it to `wrap` will allow the items to wrap to the next row or column. `nowrap` (default) will prevent your items from wrapping and shrink them if needed.
#### `justify-content`
- determines how the items inside a flex container are positioned along the main axis, affecting their position and the space around them, has 6 possible values:
	- flex-start (default)
	- flex-end
	- center
	- space-between
	- space-around
	- space-evenly
#### `align-items` 
- positions the flex content along the cross axis, and has 6 possible values:
	- stretch (default)
	- flex-start
	- flex-end
	- center
	- baseline
#### `align-content`
- determines #add 
	- stretch (default)
	- flex-start
	- flex-end
	- center
	- space-between
	- space-around

### Item Properties
#### `align-self`
#### `order`
#### `flex-grow`
#### `flex-shrink`
#### `flex-basis`




The `::after` pseudo-element creates an element that is the last child of the selected element. You can use it to add an empty element after the last image. If you give it the same `width` as the images it will push the last image to the left when the gallery is in a two-column layout. Right now, it is in the center because you set `justify-content: center` on the flex container.

Example:

```css
.container::after {
  content: "";
  width: 860px;
}
```





