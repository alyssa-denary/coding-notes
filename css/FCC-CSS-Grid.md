#refactor 
- Google font api
```
<link src="https://fonts.googleapis.com/css?family=Anton%7CBaskervville%7CRaleway&display=swap">
```
- Font awesome
```
<link src="https://use.fontawesome.com/releases/v5.8.2/css/all.css">
```
- The `loading` attribute on an `img` element can be set to `lazy` to tell the browser not to fetch the image resource until it is needed (as in, when the user scrolls the image into view). As an additional benefit, lazy loaded elements will not load until the non-lazy elements are loaded - this means users with slow internet connections can view the content of your page without having to wait for the images to load.
    Give your new `img` element a `loading` attribute set to `lazy`.
- The `Referer` HTTP header contains information about the address or URL of a page that a user might be visiting from. This information can be used in analytics to track how many users from your page visit freecodecamp.org, for example. Setting the `rel` attribute to `noreferrer` omits this information from the HTTP request. Give your `a` element a `rel` attribute set to `noreferrer`.
- Create an `html` selector and give it a `font-size` property set to `62.5%`. This will set the default font size for your web page to 10px (the browser default is 16px). This will make it easier for you to work with `rem` units later, as `2rem` would be 20px. Also, set the `box-sizing` property to `border-box`.
- Create an `img` selector and give it a `width` property set to `100%`, and an `object-fit` property set to `cover`.
    The `object-fit` property tells the browser how to position the element within its container. In this case, `cover` will set the image to fill the container, cropping as needed to avoid changing the aspect ratio.
- The `::first-letter` pseudo-selector allows you to target the first letter in the text content of an element.
    Create a `.first-paragraph::first-letter` selector and set the `font-size` property to `6rem`.
- The other text has been shifted out of place. Move it into position by giving the `.first-paragraph::first-letter` selector a `float` property set to `left` and a `margin-right` property set to `1rem`. #questions float property?
- A quote is not really a quote without proper quotation marks. You can add these with CSS pseudo selectors.
    Create a `.quote::before` selector and set the `content` property to `"` with a space following it.
    Also, create a `.quote::after` selector and set the `content` property to `"` with a space preceding it.
- Create a `.lists` selector and set the `list-style-type` property to `none`. This will get rid of the bullet points on the list items.

## CSS Grid
- CSS Grid offers a two-dimensional grid-based layout, allowing you to center items horizontally and vertically while still retaining control to do things like overlap elements. Begin by creating a `main` selector and giving it a `display` property set to `grid`.
- Now you can style the layout of your grid. CSS Grid is similar to Flexbox in that it has a special property for both the parent and child elements. In this case, your parent element is the `main` element. Set the content to have a three-column layout by adding a `grid-template-columns` property with a value of `1fr 94rem 1fr`. This will create three columns where the middle column is `94rem` wide, and the first and last columns are both 1 fraction of the remaining space in the grid container.
- Use the `minmax` function to make your columns responsive on any device. The `minmax` function takes two arguments, the first being the minimum value and the second being the maximum. These values could be a length, percentage, `fr`, or even a keyword like `max-content`. Wrap each of your already defined values of the `grid-template-columns` property in a `minmax` function, using each value as the second argument. The first argument should be `2rem`, `min-content`, and `2rem` respectively.
- To add space between rows in the grid layout, you can use the `row-gap` property. Give the `main` selector a `row-gap` property of `3rem`.
- Your magazine will have three primary sections. You already set the overall layout in the `main` rule, but you can adjust the placement in the child rules.
    One option is the `grid-column` property, which is shorthand for `grid-column-start` and `grid-column-end`. The `grid-column` property tells the grid item which grid line to start and end at.
    Create a `.heading` rule and set the `grid-column` property to `2 / 3`. This will tell the `.heading` element to start at grid line 2 and end at grid line 3.
- For additional control over the layout of your content, you can have a CSS Grid within a CSS Grid. Set the `display` property of your `.heading` selector to `grid`.
- Now you can style the content of the `.heading` element with CSS Grid.
    The CSS `repeat()` function is used to repeat a value, rather than writing it out manually, and is helpful for grid layouts. For example, setting the `grid-template-columns` property to `repeat(20, 200px)` would create 20 columns each `200px` wide.
    Give your `.heading` element a `grid-template-columns` property set to `repeat(2, 1fr)` to create two columns of equal width.
- Remember that the `grid-column` property determines which columns an element starts and ends at. There may be times where you are unsure of how many columns your grid will have, but you want an element to stop at the last column. To do this, you can use `-1` for the end column.
    Create a `.hero` selector and give it a `grid-column` property set to `1 / -1`. This will tell the element to span the full width of the grid.
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