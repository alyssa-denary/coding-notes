#refactor 
The border of the last `fieldset` element looks a little out of place. You can select the last element of a specific type using the `last-of-type` CSS pseudo-class, like this:

```css
p:last-of-type { }
```

That will select the last `p` element. Create a new selector that targets the last `fieldset` element and set its `border-bottom` to `none`.


### attribute selectors
To style the submit button, you can use an _attribute_ selector, which selects an element based on the given attribute value. Here is an example:

```css
input[name="password"]
```

The above selects `input` elements with a `name` attribute value of `password`.


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

