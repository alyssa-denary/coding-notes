### Users and groups
- When typing $ls -lah   into terminal from the home folder, should see something like this:
![[Permissions & Links-1667496609818.jpeg]]
	- 1st column: Permissions
	- 2nd column: Number of files (for files, this will always be 1)
	- 3rd column: user
	- 4th column: group
	- 5th column: size of file
	- 6th column: last date file was modified
	- 7th column: name of file

### Permissions
-  There are 3 types of operations that can be allowed or not allowed:
	  1. `r` - reading the file
	  2. `w` - writing to the file
	  3. `x` - executing the file (we will go into this in more detail soon)
-   You may be one of 3 different types of users:
	1.  The owner of the file.
	2.  Not the owner, but a member of a group associated with the file.
	3.  Other. Not an owner and not in a group that is associated with the file
- A permissions string specifies permissions for all 3 user types, with each of the 3 operations ![[Permissions & Links-1667497312442.jpeg]] 
	- If a permission is not allowed a `-` is used in its place. 

#### Changing Permissions
- To change permissions use the $chmod command
- **Octal Notation:** For each user group, can specify numerical permission from 0-7, according to chart below:![[Screen Shot 2022-11-03 at 1.47.29 PM.png]]
	- Octal Notation Examples:
		- $chmod 770 somefile.txt 
-  **Symbolic Notation**:
  (source: https://askubuntu.com/questions/518259/understanding-chmod-symbolic-notation-and-use-of-octal)![[Permissions & Links-1667595006110.jpeg]]
- Symbolic Notation Examples:
	- $chmod ug+rwx,o-rwx hi.txt
- Folders: To change permissions for a folder, must add the `-R` flag
	- $chmod -R 755   some_folder
	- $chmod -R u+rwx,go=rx   some_folder

##  Executable Files and Folders
- Executable folder means you can $cd into that folder
- Executable file means you can run the file from your shell like a program

## Changing ownership of files
- To change owner and group:
	- $chown anotheruser:anothergroup somefile.txt
- To change just the group:
	- $chown anothergroup somefile.txt

## Root user and sudo
- root is a special user that has the power to do anything it wants
- if you see root as the owner of a file/folder, and you want to do something with that, you have to use $sudo command.
- $sudo gives you the powers of the root user for just that one command

## Links
- Can create link using $ln command
- $ln   path_to_link   name_of_link

### Hard Links
- Hard links are essentially another copy of a file. If you delete the original file, the hard link still exists, and shows file's contents. 
### Symbolic Links
- Usually when linking a file, want a reference to that file and not a direct copy.
- This is what a symbolic link is. 
- To create a symbolic link, add the -s flag
	- $ln -s learn_again.txt first_sym_link
- Note that symbolic links DO break if original files/folders are deleted or moved
