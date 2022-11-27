#refactor 
The border of the last `fieldset` element looks a little out of place. You can select the last element of a specific type using the `last-of-type` CSS pseudo-class, like this:

```css
p:last-of-type { }
```

That will select the last `p` element. Create a new selector that targets the last `fieldset` element and set its `border-bottom` to `none`.


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

### pseudo-selectors

- The `:not` pseudo-selector can be used to select all elements that do not match the given CSS rule.

```css
div:not(#example) {
  color: red;
}
```

The above selects all `div` elements without an `id` of `example`.

- The :before pseudo-selector #add 
```css
p:before {
	content: "Question #";
}
```

- The `:first-of-type` pseudo-selector is used to target the first element that matches the selector. 
- The `:last-of-type` pseudo-selector does the exact opposite - it targets the last element that matches the selector.
- The `:nth-of-type()` pseudo-selector is used to target specific elements based on their order among siblings of the same type
- The `::before` selector creates a **pseudo-element** which is the first child of the selected element, while the `::after` selector creates a pseudo-element which is the last child of the selected element. 
	- To create the black keys, add a new `.key.black--key::after` selector. This will target the elements with the class `key black--key`, and select the pseudo-element after these elements in the HTML. #refactor 
	- In the new selector, set the `background-color` to `#1d1e22`. Also set the `content` property to `""`. This will make the pseudo-elements empty.
	- The `content` property is used to set or override the content of the element. By default, the pseudo-elements created by the `::before` and `::after` pseudo-selectors are empty, and the elements will not be rendered to the page. Setting the `content` property to an empty string `""` will ensure the element is rendered to the page while still being empty.

```css
tr.total td:nth-of-type(3) {
	padding-right: 0.5rem;
}
```
- The `:not()` pseudo-selector is used to target all elements that do not match the selector - in this case, any of your `span` elements that do not have the `sr-only` class. This ensures that your earlier rules for the `span[class~="sr-only"]` selector are not overwritten.
	- ex: `span:not(.sr-only)`




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

