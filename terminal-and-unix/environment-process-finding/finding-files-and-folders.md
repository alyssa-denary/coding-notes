## find
- Very useful for finding files and folders, just type find and the name of the file/folder
	- if you are finding a folder, terminal will also find & list all of the contents of that folder
```
find Downloads
```
- Advanced searches combine:
1. find
2. flags (optional)
3. a path
4. an expression
	1. primaries
	2. operands
```
find . -name "*.html"
```
path =  `.`   (indicating all paths)
expression = `-name “*.html”`     (-name is a primary, with `"*.html"` as it’s pattern argument)

## wildcard characters
`*`    -any number of characters
`?`    -one character
`[]`  -any of the characters inside the brackets

## grep
- Helpful for finding specific values in a string or text file
- Contains:
1. grep
2. flags (optional)
3. pattern
4. filename
- Can also use with piping and `cat`