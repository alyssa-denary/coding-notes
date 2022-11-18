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