The `@media` at-rule, also known as a media query, is used to conditionally apply CSS. Media queries are commonly used to apply CSS based on the viewport width using the `max-width` and `min-width` properties.

In the below example the padding is applied to the `.card` class when the viewport is `960px` wide and below.

```css
@media (max-width: 960px) {
  .card {
    padding: 2rem;
  }
}
```

Add a media query that will be applied when the viewport is `768px` wide and below.