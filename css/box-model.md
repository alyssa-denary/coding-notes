![[box-model-1669248256787.jpeg]]![[box-model-1669248350436.jpeg]]

In the CSS box model, every HTML element is treated as a box with four areas.

Imagine you receive a box from your favorite online retailer -- the content is the item in the box, or in our case, a header, paragraph, or image element.

The content is surrounded by a space called padding, similar to how bubble wrap separates an item from the box around it.

Think of the border like the cardboard box your item was shipped in.

Margin is the area outside of the box, and can be used to control the space between other boxes or elements.

Here the bottom element has a larger top margin, pushing it further down the page.

```css
.selector {
overflow: hidden;  /* overflow is related to margin *
}
```

- Filter property: option to blur elements

```css
p {
  filter: blur(3px);
}
```

- box-shadow property: Increase the area and soften the edges of `.one` by setting its `box-shadow` to `0 0 3px 3px #efb762`.
```css
.one {
box-shadow: 0 0 3px 3px #efb762;
}
```

- transform property: rotates element by specified degrees
	- negative rotation: counter-clockwise
	- positive rotations: clockwise
```css
.selector {
transform: rotate(-0.6deg);
}
```
