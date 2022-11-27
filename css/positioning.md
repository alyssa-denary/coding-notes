#add  
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