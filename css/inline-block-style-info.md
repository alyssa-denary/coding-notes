#refactor 
Center the `form` element, by giving it a `margin` of `0 auto`. Then, fix its size to a maximum width of `500px`, and a minimum width of `300px`. In between that range, allow it to have a `width` of `60vw`.

```css
form {

margin: 0 auto;

max-width: 500px;

min-width: 300px;

width: 60vw;

}
```
- To center use auto margins left and right
- center text can use text-align: center

`width`: `unset`; 
unsets previously set width, useful if undoing previously set width for a class

```css
.inline {

width: unset;

margin: 0 0.5em 0 0;

vertical-align: middle;

}
```