#refactor 
- The `loading` attribute on an `img` element can be set to `lazy` to tell the browser not to fetch the image resource until it is needed (as in, when the user scrolls the image into view). As an additional benefit, lazy loaded elements will not load until the non-lazy elements are loaded - this means users with slow internet connections can view the content of your page without having to wait for the images to load.
    Give your new `img` element a `loading` attribute set to `lazy`.
- The `Referer` HTTP header contains information about the address or URL of a page that a user might be visiting from. This information can be used in analytics to track how many users from your page visit freecodecamp.org, for example. Setting the `rel` attribute to `noreferrer` omits this information from the HTTP request. Give your `a` element a `rel` attribute set to `noreferrer`.
- Create an `html` selector and give it a `font-size` property set to `62.5%`. This will set the default font size for your web page to 10px (the browser default is 16px). This will make it easier for you to work with `rem` units later, as `2rem` would be 20px. Also, set the `box-sizing` property to `border-box`.
- Create an `img` selector and give it a `width` property set to `100%`, and an `object-fit` property set to `cover`.
    The `object-fit` property tells the browser how to position the element within its container. In this case, `cover` will set the image to fill the container, cropping as needed to avoid changing the aspect ratio.
- The `::first-letter` pseudo-selector allows you to target the first letter in the text content of an element.
    Create a `.first-paragraph::first-letter` selector and set the `font-size` property to `6rem`.
- The other text has been shifted out of place. Move it into position by giving the `.first-paragraph::first-letter` selector a `float` property set to `left` and a `margin-right` property set to `1rem`. #questions float property?
- A quote is not really a quote without proper quotation marks. You can add these with CSS pseudo selectors.
    Create a `.quote::before` selector and set the `content` property to `"` with a space following it.
    Also, create a `.quote::after` selector and set the `content` property to `"` with a space preceding it.
- Create a `.lists` selector and set the `list-style-type` property to `none`. This will get rid of the bullet points on the list items.

