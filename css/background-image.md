```css
.header {
	height: 95vh; /**/
	background-image: url(../img/hero.jpg);
	background-size: cover;
	background-position: top;
}
```

## background-size
- cover:  Scales the image (while preserving its ratio) to the smallest possible size to fill the container (that is: both its height and width completely _cover_ the container), leaving no empty space. If the proportions of the background differ from the element, the image is cropped either vertically or horizontally.
- contain: Scales the image as large as possible within its container without cropping or stretching the image. If the container is larger than the image, this will result in image tiling, unless the [`background-repeat`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-repeat) property is set to `no-repeat`.
- width (absolute or %, height is auto)
- widht and height (in absolute or %)

## background-position
- background-position specifies where you want to position your image, so that when the screen is resized, that part of the image stays stable while other pieces are cropped.
	- top: keeps the top of the image in place, will crop out bottom and sides as needed
	- bottom: keeps bottom of image in place, will crop out top and sides as needed
	- center: keeps image centered, will crop out top/bottom and sides as needed

## gradients
- To specify gradients, always use background-image property
- Gradients in CSS are a way to transition between colors across the distance of an element. They are applied to the `background` property and the syntax looks like this:

```css
.selector {
	background-image: gradient-type(
		gradient-direction,
		color1,
		color2
	);
```

- In the example, `color1` is solid at the top, `color2` is solid at the bottom, and in between it transitions evenly from one to the next.

### gradient-type
- linear-gradient()
	- repeating-linear-gradient()
- radial-gradient()
	- repeating-radial-gradient()
- conic-gradient()
	- repeating-conic-gradient()
- `repeating`  gradients will make the colors of your gradient repeat until it gets to the bottom of the element; giving you some stripes, and saving you from having to add a bunch of elements to create them.

### gradient-direction
- Default is top to bottom
- Can change to:
	- Horizontal: to right, to left
	- Diagonal: to bottom right, to top left, etc. 
	- Specific angle: 70deg, 90deg, etc. 
	  
### gradient transitions
-  Default is evenly spaced colors
- You can specify where colors stop/ where you want to transition by adding a percentage or absolute value to the color like this:

```css
gradient-type(
  color1,
  color2 20%,
  color3
);
```

- Here, it will transition from `color1` to `color2` between `0%` and `20%` of the element and then transition to `color3` for the rest. 
- Gradient transitions often gradually change from one color to another. You can make the change a solid line like this:

```css
linear-gradient(
  var(--first-color) 0%,
  var(--first-color) 40%,  /* same value */
  var(--second-color) 40%, /* same value */
  var(--second-color) 80%
);
```

 - You can see the hard color change at the top of the section. 

### mulitiple gradients
- You can add multiple gradients to an element by separating them with a comma (`,`) like this:

```css
gradient1(
  colors
),
gradient2(
  colors
);
```

## multiple background-images
- background-images render in an order
	- if you want a particular image/gradient on top, should be first in CSS
```css
.header {
	height: 95vh;
	background-image: linear-gradient(
		to right bottom,
		rgba(126, 213, 111, 0.8),
		rgba(40, 180, 131, 0.8)), /* Note end of gradient code here */
		url(../img/hero.jpg); /* Note second background img here */
	background-size: cover;
	background-position: top;
}
```



