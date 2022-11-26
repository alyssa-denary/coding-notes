Continuing with the `meta` elements, a `viewport` definition tells the browser how to render the page. Including one betters visual accessibility on mobile, and improves _SEO_ (search engine optimization).

Another important `meta` element for accessibility and SEO is the `description` definition. The value of the `content` attribute is used by search engines to provide a description of your page.

Notice these meta elements have  `name` and `content` attributes.
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />

<meta name="description" content="freeCodeCamp Accessibility Quiz practice project" />
```

Lastly in the `head`, the `title` element is useful for screen readers to understand the content of a page. Furthermore, it is an important part of _SEO_. (15+ characters)

Navigation is a core part of accessibility, and screen readers rely on you to provide the structure of your page. This is accomplished with semantic HTML elements.

### SVG
A useful property of an _SVG_ (scalable vector graphics) is that it contains a `path` attribute which allows the image to be scaled without affecting the resolution of the resultant image.


### role
To increase the page accessibility, the `role` attribute can be used to indicate the purpose behind an element on the page to assistive technologies. The `role` attribute is a part of the _Web Accessibility Initiative_ (WAI), and accepts preset values.

- Every `region` role requires a visible label, which should be referenced by the `aria-labelledby` attribute.

To the `section` elements, give the following `aria-labelledby` attributes:

-   `student-info`
-   `html-questions`
-   `css-questions`


Typeface plays an important role in the accessibility of a page. Some fonts are easier to read than others, and this is especially true on low-resolution screens.
-web safe fonts: #add 

Even though you added a `placeholder` to the first `input` element in the previous lesson, this is actually not a best-practice for accessibility; too often, users confuse the placeholder text with an actual input value - they think there is already a value in the input.

### Screen Readers
Arguably, `D.O.B.` is not descriptive enough. This is especially true for visually impaired users. One way to get around such an issue, without having to add visible text to the label, is to add text only a screen reader can read.

The `.sr-only` text is still visible. There is a common pattern to visually hide text for only screen readers to read.

This pattern is to set the following CSS properties:

```css
position: absolute;
width: 1px;
height: 1px;
padding: 0;
margin: -1px;
overflow: hidden;
clip: rect(0, 0, 0, 0);
white-space: nowrap;
border: 0;
```

Use the above to define the `sr-only` class.

Although not required for `label` elements with a nested `input`, it is still best-practice to explicitly link a `label` with its corresponding `input` element.

Two final semantic HTML elements for this project are the `footer` and `address` elements. The `footer` element is a container for a collection of content that is related to the page, and the `address` element is a container for contact information for the author of the page.
The `address` element does not have to contain a physical geographical location. It can be used to provide a link to the subject.

### Visual contrast
On the topic of visual accessibility, contrast between elements is a key factor. For example, the contrast between the text and the background of a heading should be at least 4.5:1.

Change the font color of all the anchor elements within the list elements to something with a contrast ratio of at least 7:1.


### Reducing motion
Certain types of motion-based animations can cause discomfort for some users. In particular, people with vestibular disorders have sensitivity to certain motion triggers.

The `@media` at-rule has a media feature called `prefers-reduced-motion` to set CSS based on the user's preferences. It can take one of the following values:

-   `reduce`
-   `no-preference`

```css
@media (feature: value) {
  selector {
    styles
  }
}
```

---

Wrap the style rule that sets `scroll-behavior: smooth` within an `@media` at-rule with the media feature `prefers-reduced-motion` having `no-preference` set as the value.


### Keyboard shortcuts
Finally, the navigation accessibility can be improved by providing keyboard shortcuts.

The `accesskey` attribute accepts a space-separated list of access keys. For example:

```html
<button type="submit" accesskey="s">Submit</button>
```

Give each of the navigation links a single-letter access key.

_Note: It is not always advised to use access keys, but they can be useful_