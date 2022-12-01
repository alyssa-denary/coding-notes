- Selectors themselves can come in the order of the flow of the page. For example:

your css file
```
:root {all variables}

*, *::before, *::after {all resets}

body {all other global styles}

header{}

section1{}

// other related, properties alphabetized

section2{}

// other related, properties alphabetized

footer{}
```

- Properties within a selector can be alphabetized