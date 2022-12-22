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


## CSS Grid 
#refactor 
- For additional control over the layout of your content, you can have a CSS Grid within a CSS Grid. Set the `display` property of your `.heading` selector to `grid`.
- Now you can style the content of the `.heading` element with CSS Grid.
    The CSS `repeat()` function is used to repeat a value, rather than writing it out manually, and is helpful for grid layouts. For example, setting the `grid-template-columns` property to `repeat(20, 200px)` would create 20 columns each `200px` wide.
    Give your `.heading` element a `grid-template-columns` property set to `repeat(2, 1fr)` to create two columns of equal width.
- The default settings for CSS Grid will create additional rows as needed, unlike Flexbox.
- If you wanted to add more social icons, but keep them on the same row, you would need to update `grid-template-columns` to create additional columns. As an alternative, you can use the `grid-auto-flow` property.
    This property takes either `row` or `column` as the first value, with an optional second value of `dense`. `grid-auto-flow` uses an auto-placement algorithm to adjust the grid layout. Setting it to `column` will tell the algorithm to create new columns for content as needed. The `dense` value allows the algorithm to backtrack and fill holes in the grid with smaller items, which can result in items appearing out of order.
    For your `.social-icons` selector, set the `grid-auto-flow` property to `column`.
- Now the auto-placement algorithm will kick in when you add a new icon element. However, the algorithm defaults the new column width to be `auto`, which will not match your current columns.
    You can override this with the `grid-auto-columns` property. Give the `.social-icons` selector a `grid-auto-columns` property set to `1fr`.
- Much like Flexbox, with CSS Grid you can align the content of grid items with `align-items` and `justify-items`. `align-items` will align child elements along the column axis, and `justify-items` will align child elements along the row axis.
- Your `.text` element is not a CSS Grid, but you can create columns within an element without using Grid by using the `column-width` property.
- Magazines often use justified text in their printed content to structure their layout and control the flow of their content. While this works in printed form, justified text on websites can be an accessibility concern, for example presenting challenges for folks with dyslexia.
    To make your project look like a printed magazine, give the `.text` selector a `text-align` property set to `justify`.
- The images should be within a two column, three row layout. Give the `.image-wrapper` selector a `grid-template-columns` property set to `2fr 1fr` and a `grid-template-rows` property set to `repeat(3, min-content)`. This will give our grid rows that adjust in height based on the content, but columns that remain a fixed width based on the container.
- The `gap` property is a shorthand way to set the value of `column-gap` and `row-gap` at the same time. If given one value, it sets the `column-gap` and `row-gap` both to that value. If given two values, it sets the `row-gap` to the first value and the `column-gap` to the second.
- The `place-items` property can be used to set the `align-items` and `justify-items` values at the same time. The `place-items` property takes one or two values. If one value is provided, it is used for both the `align-items` and `justify-items` properties. If two values are provided, the first value is used for the `align-items` property and the second value is used for the `justify-items` property.