### Inline-block
- Only takes up the width of the content unless width is explicitly stated
- So in below example, text-align property is not visibly different 
```html
<article class="item">
	<p class="flavor">French Vanilla</p>
	<p class="price">3.00</p>
</article>
```

```css
.item p {
display: inline-block;
}

.flavor {
text-align: left;
}

.price {
text-align: right;
}
```
![[Screen Shot 2022-11-10 at 8.15.51 AM.png]]
