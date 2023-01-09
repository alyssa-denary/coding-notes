## One file
- Selectors themselves can come in the order of the flow of the page. For example:
your css file:
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

## Multiple files
- Typical to separate out css into multiple smaller files to make things easier to find and modify - see  [[7-1-file-architecture]]

### File Structure: 
(example from [[7-1-file-architecture]] scss)
- `abstracts`
	- `_functions.scss`
	- `_mixins.scss`
	- `_variables.scss`
- `base`
	- `_animations.scss`
	- `_base.scss`
	- `_typography.scss`
	- `_utilities.scss`
- `components`
	- `_bg-video.scss`
	- `_form.scss`
	- `_popup.scss`
	- `_story.scss`
- `layout`
	- `_footer.scss`
	- `_grid.scss`
	- `_header.scss`
	- `_navigations.scss`
- `pages`
	- `_home.scss`