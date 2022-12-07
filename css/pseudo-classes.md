- pseudo-classes are special states of a selector.
	- hover, link, visited checkbox clicked, etc. 
	- used to style elements under a special conditions
- The `:not` pseudo-selector can be used to select all elements that do not match the given CSS rule.

```css
div:not(#example) {
  color: red;
}
```

The above selects all `div` elements without an `id` of `example`.

- The `:first-of-type` pseudo-selector is used to target the first element that matches the selector. 
- The `:last-of-type` pseudo-selector does the exact opposite - it targets the last element that matches the selector.
	-  You can select the last element of a specific type using the `last-of-type` CSS pseudo-class, like this, which will select the last `p` element:

```css
p:last-of-type { }
```

- The `:nth-of-type()` pseudo-selector is used to target specific elements based on their order among siblings of the same type
  
```css
tr.total td:nth-of-type(3) {
	padding-right: 0.5rem;
}
```
- The `:not()` pseudo-selector is used to target all elements that do not match the selector - in this case, any of your `span` elements that do not have the `sr-only` class. This ensures that your earlier rules for the `span[class~="sr-only"]` selector are not overwritten.
	- ex: `span:not(.sr-only)`

