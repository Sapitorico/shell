# Shell, init files, variables and expansions
man or help:

* printenv
* set
* unset
* export
* alias
* unalias
* .
* source
* printf
# Tasks
### 0. <o>
Create a script that creates an alias.

Name: ls
Value: rm *

`alias ls='rm *' `

An alias is defined for each name whose value is supplied

### 1. Hello you
Create a script that prints hello user, where user is the current Linux user.

`echo "Hello $USER"`
# 2. The path to success is to take massive, determined action
Add /action to the PATH. /action should be the last directory the shell looks into when looking for a program.

`export PATH=$PATH./action `

Export - set the export attribute for the variables
# 3. If the path be beautiful, let us not ask where it leads
Create a script that counts the number of directories in the PATH.

`echo $PATH | tr ':' '\n'´ | wc -l `
# 4. Global variables
Create a script that lists environment variables.

`printenv`

printenv - prints all or part of the environment
# 5. Local variables
Create a script that lists all local variables and environment variables, and functions.

`set`

lists all local variables and environment variables, and functions in linux

# 6. Local variable
Create a script that creates a new local variable.

Name: BEST
Value: School

`export BEST="School"`
