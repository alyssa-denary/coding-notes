## Google Font API
```
<link src="https://fonts.googleapis.com/css?family=Anton%7CBaskervville%7CRaleway&display=swap">
```

## Font Awesome
FontAwesome is a library of SVG-powered icons, many of which are freely available to use. You will be using some of these icons in this project, so you will need to link the external stylesheet to your HTML.
```
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.2/css/all.css">
```

The `i` element is used for idiomatic text, or text that is separate from the "normal" text content. This could be for _italic_ text, such as scientific terms, or for icons like those provided by FontAwesome.

Within your `white-paper` element, add four `i` elements. Give them all a `class` value of `fas fa-music`.

This special class is how FontAwesome determines which icon to load. `fas` indicates the category of icons (FontAwesome Solid, here), while `fa-music` selects the specific icon.

```html
<div id="white-paper">
	<i class="fas fa-music"></i>
	<i class="fas fa-music"></i>
	<i class="fas fa-music"></i>
	<i class="fas fa-music"></i>
</div>
```
Pre-styling applied (colors are from other elements):
![[font-icons-1669570329549.jpeg]]
FontAwesome icons come with their own styling to define the icon. However, you can still set the styling yourself as well, to change things like the color and size. For now, use a `class` selector to target your `fa-music` icons.

With the following CSS applied:
```css
.fa-music {
	display: inline-block;
	margin-top: 8%;
	margin-left: 13%;
}
```

![[font-icons-1669570456970.jpeg]]

