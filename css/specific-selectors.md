
### attribute selectors
The `[attribute="value"]` selector targets any element that has an attribute with a specific value.
#refactor 
- Here is an example:

```css
input[name="password"]
```

- The above selects `input` elements with a `name` attribute value of `password`.

- The `span[class]` syntax will target any `span` element that has a `class` attribute set, regardless of the attribute's value.
- The key difference between `tr[class="total"]` and `tr.total` is that the first will select `tr` elements where the _only_ class is `total`. The second will select `tr` elements where the class _includes_ total.

### ! Important Keyword
Rather than having to constantly double-check you are not overwriting your earlier properties, you can use the `!important` keyword to ensure these properties are always applied, regardless of order or specificity.
- example:
```css
span[class~="sr-only"] {
	border: 0 !important;
	clip: rect(1px, 1px, 1px, 1px) !important;
	clip-path: inset(50%) !important;
	-webkit-clip-path: inset(50%) !important;
	height: 1px !important;
	width: 1px !important;
	position: absolute !important;
	overflow: hidden !important;
	white-space: nowrap !important;
	padding: 0 !important;
	margin: -1px !important;
}
```

