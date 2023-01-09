- Flexbox is a one-dimensional CSS layout that can control the way items are spaced out and aligned within a container.
	- For two-dimensional layouts, see [[grid]]
- Main idea of flexbox: gives container ability to expand and shrink elements to best use available space. (replaces float layouts)

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
- defines positioning of items along the main axis, and has 6 possible values:
	- flex-start (default)
	- flex-end
	- center
	- space-between
	- space-around
	- space-evenly
#### `align-items` 
- defines positioning of items along the cross axis, and has 5 possible values:
	- stretch (default)
	- flex-start
	- flex-end
	- center
	- baseline  - aligns text within items along a baseline
#### `align-content`
- only applies when there is more than 1 row of flex content
-  aligns rows along the cross axis, has 6 possible values:
	- stretch (default)
	- flex-start
	- flex-end
	- center
	- space-between
	- space-around

### Item Properties
##### `align-self`
- Similar to align-items, but for 1 individual item, has 5 possible values:
	- stretch (default)
	- flex-start
	- flex-end
	- center
	- baseline
##### `order`
- defines order which 1 specific flex item should appear inside container.
- Useful for ordering for smaller or larger screens. Orders in ascending order, and takes integer input:
	- `0` (default)
	- `<integer>`

#### Properties that determine width of flex item:

##### `flex-grow`
- Defines how much an item can grow. Value is in proportion to other item’s values. Takes integer input.
	- `0` (default)
	- `<integer>`
##### `flex-shrink`
- Defines how much an item can shrink. Value is in proportion to other item’s values. Takes integer input
	- `1` (default)
	- `<integer>`
##### `flex-basis`
- Defines base width, used instead of defining width on a flex item. Takes integer input
	- `auto` (default)
	- `<length>`

##### `flex` (shorthand):
`flex`:  `flex-grow` |  `flex-shrink` | `flex-basis`





