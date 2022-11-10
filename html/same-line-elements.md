### Same-line-elements
- Putting p elements on the same line modified spacing (padding? margin?) of the page
```html
<article class="item">
<p class="flavor">French Vanilla</p><p class="price">3.00</p>
</article>
```
##### Before:
- HTML p elements on separate lines
- CSS styling for width for .flavor and .price set to 49%, as 50% set flavor and price to separate lines (due to padding or margin on each).
- Note slight gap between price and edge of container on right side. 
![[Screen Shot 2022-11-10 at 8.29.57 AM.png]]

##### After:
- HTML p elements on same line
- CSS styling for width for .flavor and .price set to 50%
