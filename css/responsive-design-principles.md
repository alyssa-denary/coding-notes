Cite: Jonas advanced css udemy course

## 1. Fluid Layouts
- Purpose is to allow the webpage to adapt to current viewport width or height
- Can easily accomplish this by using %, vw, or vh units instead of pixel unit 
	- for all units that should adapt to the viewport (usually layout elements)
- Use max-width instead of width
### Layout Types
- Float layouts: Old way, mostly outdated
- Flexbox: One of the modern ways, perfect for one dimensional layouts
- CSS grid: For laying out elements in 
## 2. Responsive Units
- Use rem unit instead of px for most lengths
	- makes it easy to scale entire website up or down as needed
## 3. Flexible images
- Images don’t by default scale as the viewport is changed
- Always use % for image dimensions
	- along with max-width property
## 4. Media queries
- To change CSS styles on certain viewport widths
	- (also called breakpoints)
### Mobile-first vs Desktop-first
#### Desktop-first
- Start by designing for larger screens
- Write media queries for smaller screens
- Advantages: 
- Disadvantages: May have extra unneeded stuff
#### Mobile-first
- Start by desigining for smaller screens
- Write media queries for larger screens
- Forces distilling down a website to essential components, smaller and faster final product
- Advantages: Many many users accessing sites via phones/smaller screens
- Distadvantages: Desktop versions in this strategy may feel stripped down

- & Takeaway: Keep in mind the purpose of the website, and design with that in mind
- & Always design / keep in mind both desktop and mobile versions, regardless of strategy

### Breakpoints
- Three major ways to choose breakpoints
	- Bad: Choosing ipad/iphone (or any specific device) widths to determine breakpoints
	- Good: Use most used devices widths to determine breakpoints
		- Can look up this data on StatCounter
	- Perfect: Ignore devices altogether and only worry about your content and design. Put breakpoints wherever your design starts to look weird. 


