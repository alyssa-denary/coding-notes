#refactor 
- `overflow` property to `hidden` to hide any scroll bars that appear when something extends past the viewport.
- width/height: When is width and height relative to parent vs relative to document or viewport #questions 
- Variable declarations begin with two dashes (`-`) and are given a name and a value like this: `--variable-name: value;`
- To use a variable, put the variable name in parentheses with `var` in front of them like this: `var(--variable-name)`. Whatever value you gave the variable will be applied to whatever property you use it on.
- This is the main advantage of using variables, being able to quickly change many values in your stylesheet by just changing the value of a variable.
- You will be using almost all percent based units and some flexbox for this project, so everything will be completely responsive.
- You should add a fallback value to a variable by putting it as the second value of where you use the variable like this: `var(--variable-name, fallback-value)`. The property will use the fallback value when there's a problem with the variable.
- That didn't work, because the variables you declared in `.bb1` do not cascade to the `.bb2` and `.bb3` sibling elements. That's just how CSS works. Because of this, variables are often declared in the `:root` selector. This is the highest level selector in CSS; putting your variables there will make them usable everywhere. Add the `:root` selector to the top of your stylesheet, and move all your variable declarations there.
- Now that you've worked the bugs out and the buildings are the right colors, you can remove the fallback values in the two places they were used. Go ahead and do that now.

- In the next few steps, you are going to use some tricks with CSS borders to turn the `.bb2a` section into a triangle at the top of the building. 
```css
.bb2 {
	width: 10%;
	height: 50%;
}

.bb2a {
	margin: auto;
	width: 5vw;
	height: 5vw;
	border-top: 1vw solid #000;
	border-bottom: 1vw solid #000;
	border-left: 1vw solid #999;
	border-right: 1vw solid #999;
}
```
Next, remove the `width` and `height` from `.bb2a`, and change the `border-left` and `border-right` to use `5vw` instead of `1vw`. The element will now have zero size and the borders will come together in the middle.
```css
.bb2a {
	margin: auto;
	border-top: 1vw solid #000;
	border-bottom: 1vw solid #000;
	border-left: 5vw solid #999;
	border-right: 5vw solid #999;
}
```
![[FCC-css-variables-1670086616970.jpeg]]
```css
.bb2a {
	margin: auto;
	border-top: 1vw solid #000;
	border-bottom: 1vw solid #000;
	border-left: 5vw solid transparent;
	border-right: 5vw solid transparent;
}
```
![[FCC-css-variables-1670086631870.jpeg]]
Remove the `margin` and `border-top` properties and values from `.bb2a` to turn it into a triangle for the top of the building.
```css
.bb2a {
	border-bottom: 1vw solid #000;
	border-left: 5vw solid transparent;
	border-right: 5vw solid transparent;
}
```
![[FCC-css-variables-1670086727366.jpeg]]
Finally, on the `border-bottom` property of `.bb2a`, change the `1vw` to `5vh` and change the `#000` color to your `--building-color2` variable. There you go, now it looks good! At any time throughout this project, you can comment out or remove the `border` property you added to everything at the beginning to see what the buildings will look like when that gets removed at the end.
```css
.bb2a {
	border-bottom: 5vw solid var(--building-color2);
	border-left: 5vw solid transparent;
	border-right: 5vw solid transparent;
}
```
with border property on everything:
![[FCC-css-variables-1670086890869.jpeg]]
without border:
![[FCC-css-variables-1670086917527.jpeg]]


- You're going to use some more border tricks for the top section. Add a `border-bottom` with a value of `7vh solid var(--building-color4)` to `.fb1a`. This will put a `7vh` height border on the bottom. But since the element has zero size, it only shows up as a 2px wide line from the 1px border that is on all the elements.
- When you increase the size of the left and right borders, the border on the bottom will expand to be the width of the combined left and right border widths. Add `2vw solid transparent` as the value of the `border-left` and `border-right` properties of `.fb1a`. They will be invisible, but it will make the border on the bottom `4vw` wide.
- For `.fb2a`, add a `border-bottom` of `10vh solid var(--building-color3)`, and a `border-left` and `border-right` of `1vw solid transparent`. This time the border trick will create a trapezoid shape.
- Give the `sky` class a `radial-gradient`. Use `#ffcf33` from `0%` to `20%`, `#ffff66` at `21%`, and `#bbeeff` at `100%`. This will add circular gradient to the background that will be your sun.![[FCC-css-variables-1670251506095.jpeg]]
- At the top of the sky gradient color list, where you would put a direction for the gradient; add `circle closest-corner at 15% 15%,`. This will move the start of the gradient to `15%` from the top and left. It will make it end at the `closest-corner` and it will maintain a `circle` shape. These are some keywords built into gradients to describe how it behaves.![[FCC-css-variables-1670251593216.jpeg]]
- A media query can be used to change styles based on certain conditions, and they look like this:

```css
@media (condition) {

}  
```

Add an empty media query at the bottom of your stylesheet with a condition of `max-width: 1000px`. Styles added in here will take effect when the document size is 1000px wide or less.