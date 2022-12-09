## Processing CSS
1. Browser first resolves conflicting CSS properties
2. Then browser parses css, processes values

### Resolving conflicts
1. Importance
	1. User ! Important Declarations
	2. Author ! Important Declarations
	3. Author Declarations
	4. User Declarations
	5. Default browser declarations
2. Specificity 
   - if all conflicts have same importance, CSS attempts to resolve by specificity
	1. Inline styles
	2. IDs
	3. Classes, pseudo-classes, attribute
	4. Elements, pseudo-elements
	   Calculated with score on:  (inline, ids, classes, elements)
3. Source order
   - if conflicts have same importance AND specificity, CSS resolves by source order
	1. Last declaration made will override other declarations and will be applied

#### Takeaways
- & Use ! Important declarations as a last resort. Better to use correct specificity.
- & Rely on specificity vs order of selectors
- & When using external stylesheets, always put your author stylesheet last

### Calculating and rendering values
#### How CSS vals are processed
1. Declared value: author declarations
2. Cascaded value: after the cascade
3. Specified value: defaulting if no cascaded value
	1. & Each property have a initial value, which is applied at this point if nothing is declared and if there is no inheritance.
4. Computed value: converting relative units to absolute px
   - & All relative units are always converted into pixels. Here’s how:
	1. Font based:
		1. em (font): uses parent element’s font-size as reference to calculate the current elelement’s font-size
		   If parent has font-size: 16px, and child is 3em, child will be 16x3 = 48px
		2. em (length): uses current element’s font-size as reference to calc length
		   If parent has font-size: 16px, and child is using 3em length child use 16x3 = 48px for that length
		3. rem: uses root font-size as reference to calculate
		   root is typically 16px, and thus rem calculations will typically be built off of this
	2. Viewport based:
		1. vh: based on viewport height
		2. vw: based on viewport width
5. Used value: final calculations based on layout
	1. Percentage based values calculated at this step.
	2. &  Note that % are always based on the size of the parent element
		1. If used to specify font size, uses parent font-size
		2. If used to specify lengths, uses parent’s <u>width</u>
6. Actual value: browser and device restrictions

#### Inheritance
- Some properties are inherited while others are not
- If inherited, the computed value from the parent is inherited - not the declared value.
- Generally, properties related to text are inherited, while margin/padding are not.
- Only happens if author and browser do not declare value for that property
- & `inherit` keyword forces inheritance of property
- & `initial` keyword resets a property to its initial value


## Applying this knowledge
- Use rem values throughout your projects
- Then you can modify all measurements on page by just modifying the global font size 
	- via html selector
- ! Bad practice to set font size using pixels
	- because it overrides accessiblity options for users who change their default font size to larger size
- Better practice to inherit border-border box from body due to plugins, etc.


```css
*, 
*::before, 
*::after {
	margin: 0;
	padding: 0;
	box-sizing: inherit;
}

html {
	font-size: 62.5%; /* for font size of 10px, 100% for font-size 16px*/
}

body {
	font-family: "Lato", sans-serif;
	font-weight: 400;
	padding: 3rem;
	box-sizing: border-box; 
	/* Because box-sizing set to inherit above, all child elements of body will now inherit border-box */
}
```
