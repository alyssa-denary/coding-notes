## find
- Very useful for finding files and folders, just type find and the name of the file/folder
	- if you are finding a folder, terminal will also find & list all of the contents of that folder
```
find Downloads
```
- Advanced searches combine:
1. find
2. a path
3. an expression
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