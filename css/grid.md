- CSS Grid  is like a two-dimensional flexbox. 
- Allows you to center items horizontally and vertically while still retaining control to do things like overlap elements.
- CSS Grid is also similar to Flexbox in that it has a special property for both the parent and child elements. 
- Use the `minmax` function to make your columns responsive on any device. The `minmax` function takes two arguments, the first being the minimum value and the second being the maximum. These values could be a length, percentage, `fr`, or even a keyword like `max-content`.
- To add space between items in the grid layout, you can use the `grid-gap` property, or specify `row-gap` or `column-gap` separately. 

## Sizing grid items
- Two ways of sizing items:
	- using grid-template-areas
	- using grid-row & grid-column

### grid-template-areas
- Great for when you need to resize elements based on diff screen sizes
- Not the common way to use grid though
```css
.grid-container {
	display: grid;
	grid-template-columns: 200px 250px;
	grid-auto-rows: minmax(150px, auto);
	grid-template-areas: 
		"header header"
		"sidebar content"
		"sidebar content"
	grid-gap: 20px;
}

.grid-item-1 {
	grid-area: header;
}

.grid-item-2 {
	grid-area: sidebar;
}

.grid-item-3 {
	grid-area: content;
}
```
![[grid-1670455916239.jpeg]]

### grid-row & grid-column
- Much more common way of sizing
```css
.grid-container {
	display: grid;
	grid-template-columns: 200px 250px;
	grid-auto-rows: minmax(150px, auto);
	grid-gap: 20px;
}

.grid-item-1 {
	grid-column-start: 1;
	grid-column-end: 3; 
	/* For first row to stretch across width of both columns */
	/* Could also put -1 instead of 3 to span across all # columns */
	/* Could also use shorthand-  grid-column: 1 / 3;  */
}

.grid-item-2 {
	grid-row: 2 / 4;
	/* Using shorthand, for second row second column to stretch down 2 rows */
}

.grid-item-3 {
	grid-row: span 2;
	/* Another shorthand way to specify that this element will span 2 rows */
}
```
![[grid-1670456554399.jpeg]]

## Aligning grid items
-  Much like Flexbox, with CSS Grid you can align the content of grid items with `align-items` and `justify-items`. `align-items` will align child elements along the column axis, and `justify-items` will align child elements along the row axis.

### Justify & Align Content
- Justifies/Aligns grid <u>items</u> within their <u>container</u>
```css
.grid-container {
	display: grid;
	grid-template-columns: 200px 250px;
	grid-auto-rows: minmax(150px, auto);
	grid-gap: 20px;
	justify-content: start; 
	/* Note start instead of flex-start, end instead of flex-end, etc. */
	align-content: center;
	height: 100vh;
}
```
example with justify-content: center; 
![[grid-1670457866939.jpeg]]

### Justify & Align Items
- Justifies/Aligns <u>content</u> within their <u>grid row/column</u>
```css
.grid-container {
	display: grid;
	grid-template-columns: 200px 250px;
	grid-auto-rows: minmax(150px, auto);
	grid-gap: 20px;
	justify-items: center; 
	align-items: center;
}
```
![[grid-1670457995819.jpeg]]

### Justify & Align Self
- Can override group alignment with justify-self and align-self
```css
.grid-container {
	display: grid;
	grid-template-columns: 200px 250px;
	grid-auto-rows: minmax(150px, auto);
	grid-gap: 20px;
	justify-items: stretch; 
	align-items: stretch;
}

.grid-item-1 {
	align-self: start;
}
```
![[grid-1670458142888.jpeg]]

- & Web dev simplified advice: Using flexbox containers inside of your different grid items –> One of the best ways to layout a website
