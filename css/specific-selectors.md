The border of the last `fieldset` element looks a little out of place. You can select the last element of a specific type using the `last-of-type` CSS pseudo-class, like this:

```css
p:last-of-type { }
```

That will select the last `p` element. Create a new selector that targets the last `fieldset` element and set its `border-bottom` to `none`.