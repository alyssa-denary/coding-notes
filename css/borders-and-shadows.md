## Borders
The `border-left` shorthand property lets you to set the left border's width, style, and color at the same time.

Here is the syntax:

```css
border-left: width style color;
```

In the `.sleeve` CSS rule, replace the `border-left-width`, `border-left-style`, and `border-left-color` properties with the `border-left` shorthand property.

## Shadows
The last thing you'll do is add a slight shadow to each marker to make them look even more realistic.

The `box-shadow` property lets you apply one or more shadows around an element. Here is basic syntax:

```css
box-shadow: offsetX offsetY color;
```

```css
.red {
	background: linear-gradient(rgb(122, 74, 14), rgb(245, 62, 113), rgb(162, 27, 27));
	box-shadow: 5px 5px red;
}
```
As you can see, you added a simple red shadow around your marker that's 5 pixels to the right, and 5 pixels down.

But what if you wanted to position your shadow on the opposite side? You can do that by using negative values for `offsetX` and `offsetY`.

```css
.red {
	background: linear-gradient(rgb(122, 74, 14), rgb(245, 62, 113), rgb(162, 27, 27));
	box-shadow: -5px -5px red;
}
````

Notice that the edges of the shadow are sharp. This is because there is an optional `blurRadius` value for the `box-shadow` property:

```css
box-shadow: offsetX offsetY blurRadius color;
```

If a `blurRadius` value isn't included, it defaults to `0` and produces sharp edges. The higher the value of `blurRadius`, the greater the blurring effect is.

But what if you wanted to expand the shadow out further? You can do that with the optional `spreadRadius` value:

```css
box-shadow: offsetX offsetY blurRadius spreadRadius color;
```

Like `blurRadius`, `spreadRadius` defaults to `0` if it isn't included.