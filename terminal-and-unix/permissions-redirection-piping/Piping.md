Continuation of [[Redirection]]

## New Terminal Commands:

`head` - display the first lines of a file (using the `-n` flag we can specify the number of lines)
`tail` - display the last lines of a file (using the `-n` flag we can specify the number of lines)
`sort` - sort lines of a text file
`uniq` - removes duplicated lines (your data **must** be sorted for this to work)
`wc` - word, line, character and byte count
`cat` - prints file contents to terminal, or concatenates (joins) two files together
`grep` - powerful for finding text, if `grep` doesn't find a match, it won't output anything. If it finds multiple matches, it will print them all.

## Piping:
- Piping connects the output of one command into the input of another command. Use the | symbol to link two commands
	- $cat first.txt second.txt | sort
	- $cat first.txt second.txt | sort | head -n 2
- Breaking it down further:
	- cat first.txt second.txt | sort | tail -n 3 | head -n 1
		1.  Concatenate the two files first.txt and second.txt
		2.  Sort the results
		3.  Find the last 3 lines
		4.  Find the first line of those last 3 lines
		- This is how we can find the third from last line in a file (without knowing how many lines the file has).



