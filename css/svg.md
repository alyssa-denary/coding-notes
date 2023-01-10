A useful property of an _SVG_ (scalable vector graphics) is that it contains a `path` attribute which allows the image to be scaled without affecting the resolution of the resultant image.
-svg icons are better than font-icons: screen readers try to read out font-icons and fail to do so. Best practice to move away from icon fonts and instead use SVGs. 
- Icomoon: web app for using svgs


### Using with sprite
- recommended b/c only 1 http request
- can change color with css fill prop
- only works with web server
```html
<svg class="search_icon">
	<use xlink:href="img/sprite.svg#icon-magnifying-glass"></use>
</svg>
```