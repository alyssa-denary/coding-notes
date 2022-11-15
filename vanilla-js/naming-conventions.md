### const variables
1.  in the lesson about `const` , FCC teaches that the naming convention for `const`  should always be an ALL_ CAPS name.  The actual note was:

**Note:** It is common for developers to use uppercase variable identifiers for immutable values and lowercase or camelCase for mutable values (objects and arrays). You will learn more about objects, arrays, and immutable and mutable values in later challenges. Also in later challenges, you will see examples of uppercase, lowercase, or camelCase variable identifiers.This might be more of a question for [@Hideaki](https://weeklycodinglessons.slack.com/team/U03QNK5U15K), but really for anyone with work experience, does this naming convention hold true in the actual working world?

#### Hideaki:
This is mostly not true, but not entirely untrue. Do you remember the matrix algo challenge we did? We did something like  

```js
const ROW_LENGTH = 3;
const COL_LENGTH = 5;
```

I think of capitalized const values as “super” consts that are important to keep in mind for the entire scope of the function.Once we learn css-in-javascript (styled components, css-modules) in react, you’ll also start writing some styling in js. The convention there is also something like:  
```js
// in a .js file

const PADDING_DEFAULT = 2rem;
```
