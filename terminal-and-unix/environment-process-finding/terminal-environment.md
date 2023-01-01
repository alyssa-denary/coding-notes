### What is your terminal's environment?

A terminal's environment is a list of settings that can be referenced by programs. Type `env` into terminal to see what your terminal's environment looks like right now. You should see output similar to the following:
```
rvm_bin_path=/Users/tim/.rvm/bin
TERM_PROGRAM=Apple_Terminal
GEM_HOME=/Users/tim/.rvm/gems/ruby-2.3.1
TERM=xterm-256color
SHELL=/bin/bash
CLICOLOR=1
IRBRC=/Users/tim/.rvm/rubies/ruby-2.3.1/.irbrc
TMPDIR=/var/folders/5s/zstwqxy52pl_lq_lr3b5v7nc0000gn/T/
Apple_PubSub_Socket_Render=/private/tmp/com.apple.launchd.Q7TcyOvK4P/Render
TERM_PROGRAM_VERSION=361.1
OLDPWD=/Users/tim
TERM_SESSION_ID=281162A1-5C58-4285-9A35-AC9306923C34
USER=tim
__CF_USER_TEXT_ENCODING=0x1F5:0x0:0x0
LSCOLORS=GxFxCxDxBxegedabagaced
PATH=/usr/local/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Users/tim/.rvm/bin
PWD=/Users/tim/Projects/Rithm/prework
.
.
.
```
#### Environment Variables
- Each word on the left side of the equal sign is called an **environment variable**. The value on the right side is the value of the variable.
- Note that environment variables can be:
	- Process level: used just in one terminal session
		- within one program
		- system-wide (system environment variable) 
	- System level: saved to use later: 
		- within a program
		- system-wide (in .zshrc or .bash_profile files for system-wide saving), can be further divided into:
			- user-specific
			- public-specific

### Using environment variables

Use `echo` to see value of environment variable. Note, must use the `$` as a prefix.
```
echo $PWD
```

### Creating environment variables
- VARIABLE_NAME = typically uppercase with words separated by underscores
- VALUE = string

#### Environment variables
To create an environment variable within a program, simply assign the variable name to the value within the program directory
```
VARIABLE_NAME=/STRING/VALUE

INTERVAL=2
```
#### System environment variables
Use the `export` command to create an environment variable that is system-wide.
```
export VARIABLE_NAME=/STRING/VALUE

export PROJDIR=/Users/tim/Projects
```

- Notice that the `$` isn't being used in these cases. When you define an environment variable, you do not use the `$`. Only use the `$` when you want to reference the value of the variable.
-  Every time you close your terminal window, the environment variables get reset, so unless  saved in your .zshrc or .bash_profile files, the `$INTERVAL` and `$PROJDIR` environment variables would be lost.

### Saving environment variables

To save environment variables, you need to modify the shell configuration file in your home directory, either `.zshrc` or `.bash_profile`.  Add the following line to your file (for system environment variables):
```
export VARIABLE_NAME=/STRING/VALUE/

export PROJDIR=/Users/$USER/Projects
```

Save the file, quit out of all terminal windows, and then open terminal again. 
To test, execute `echo $VARIABLE-NAME`

- Note that an environment variable can be defined using other environment variables, like the example above where `$USER`  variable is used inside the value for `$PROJDIR`.

### The `PATH` environment variable

- has a list of directories
- each directory could have any program you’d like, that can be <u>executed directly from the terminal</u>
- The ability to have executable shortcuts from the terminal is the magic of the PATH variable
