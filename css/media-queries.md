The `@media` at-rule, also known as a media query, is used to conditionally apply CSS. Media queries are commonly used to apply CSS based on the viewport width using the `max-width` and `min-width` properties.

- Always put media queries at the end because they don’t add any specificity or importance, so order matters.

In the below example the padding is applied to the `.card` class when the viewport is `960px` wide and below.

```css
@media (max-width: 960px) {
  .card {
    padding: 2rem;
  }
}
```

Logical operators can be used to construct more complex media queries. The `and` logical operator is used to query two media conditions.

For example, a media query that targets a display width between 500px and 1000px would be:

```css
@media (min-width: 500px) and (max-width: 1000px){

}
```
