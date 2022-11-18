### What is your terminal's environment?

A terminal's environment is a list of settings that can be referenced by programs. To see what your terminal's environment looks like right now, try typing `env` in your terminal. You should see output similar to the following:
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
Each word on the left side of the equal sign is called an **environment variable**. The value on the right side is the value of the variable.

### Using environment variables

In the terminal, you can see what value an environment variable has by using `echo`. When referencing an environment variable, you must use the `$` as a prefix. In other words, to print the value for the environment variable `PWD`, the command would be:

echo $PWD

Try that in your terminal. You should get the same output as the output for the command `pwd`.

### Creating environment variables

Now let's make our own environment variable. Go to your home directory and create a folder called `Projects`. Now let's make an environment variable called `PROJDIR` (environment variables are usually all caps) that keeps track of the path to your projects directory. To create an environment variable, you can use the `export` command. On a Mac or Linux machine, the command would be:

```
export PROJDIR=/Users/tim/Projects
```

Notice that the `$` isn't being used in this case. When you define an environment variable, you do not use the `$`. Only use the `$` when you want to reference the value of the variable.

Now that you've created the environment variable, let's use it:
```
cd ~
cd $PROJDIR
```

You should now be in your project directory.

So now we have a great way of saving a useful variable in our terminal's environment, but we have a problem. Every time you close your terminal window, the environmet variables get reset, so the `PROJDIR` environment variable will be lost! How do we fix that?

### Saving environment variables

Now that we know how to create environment variables, we need to learn how to save them so that every time we open a new terminal window, we have those environment variables set. To save environment variables, you need to modify the shell configuration file in your home directory. This file is different depending on what your default shell is. If you are using oh-my-zsh, then your configuration file will be called `.zshrc`; if you are using bash, then your configuration file will be called `.bash_profile`.

Open the configuration file for your shell, either `.zshrc` or `.bash_profile`. Next, add the following line to your file:

```
export PROJDIR=/Users/$USER/Projects
```

Save the file, quit out of all terminal windows, and then open terminal again. Try executing `echo $PROJDIR`. You should see the path to your projects directory.

We did one other interesting thing here. Rather than using a hard coded path to the projects directory, we used another environment variable to figure out the correct user name. Try typing `echo $USER` in your terminal. You should see your user name. The important takeaway here is that an environment variable can be defined using other environment variables. For example, if we had a `python` folder inside of the `Projects` directory, we may want a variable for that as well. We could definite it like the following way:

```
export PYTHON_PROJ=/Users/$USER/Projects/python
```

Or we could use the `PROJDIR` environment variable that we already have set:

```
export PYTHON_DIR=$PROJDIR/python
```

The only catch is that the line for exporting `PROJDIR` must come before the line using `PROJDIR`. Otherwise, `PROJDIR` will not yet be defined when we use it in the `PYTHON_DIR` definition.

### The `PATH` environment variable

An important environment variable to know and understand is the `PATH`. Your terminal uses the `PATH` environment variable to find programs to execute. Try the following in a new terminal window:

```
export PATH=
```

Now try using `ls` in the terminal. It doesn't work! Try a few other commands like `man` or `chgrp`. None of them work. That's because commands like `ls` are just programs stored in a file somewhere in your filesystem. The reason we don't normally need to give the full path to the `ls` command when we use it is because `ls` is a file found in one of the folders that are specified on the path.

Open a fresh terminal window. The `ls` command should be working again. Now use the `which` command to see where on the path `ls` is coming from:

```
which ls
```

Typically, the `ls` command is located in the `/bin` directory (though if you're using oh-my-zsh, the command may be aliased to `ls -G`). Let's change our `PATH` environment variable again, but this time, let's assign it to `/bin`:

```
export PATH=/bin
```

Now try to use the ls command. It should still work! That's because `ls` can now be found in one of the folders of the `PATH`, specifically in `/bin`. Other commands still don't work however. The `man` command still isn't working because it is not found on the `PATH`. Let's add a few more directories to the `PATH` in the same terminal window. We want to add `/usr/bin`, `/usr/sbin`, and `/sbin`, but we don't want to rewrite the `PATH` variable completely. Instead, let's add to the `PATH` that already exists. In order to do that, we reference the `PATH` environment variable using the `$` and separate multiple paths using a colon:

```
export PATH=$PATH:/usr/bin:/usr/sbin:/sbin
```

Now if you do `echo $PATH`, you should see the following output:

```
/bin:/usr/bin:/usr/sbin:/sbin
```

And commands like `man` should work. Now that you understand the `PATH`, close the terminal window and open a fresh window, so that your `PATH` will be set up correctly.

When you're ready, move on to [Processes](https://www.rithmschool.com/courses/terminal/terminal-process)