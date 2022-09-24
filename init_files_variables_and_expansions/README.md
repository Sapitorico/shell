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
### 2. The path to success is to take massive, determined action
Add /action to the PATH. /action should be the last directory the shell looks into when looking for a program.

`export PATH=$PATH./action `

Export - set the export attribute for the variables
### 3. If the path be beautiful, let us not ask where it leads
Create a script that counts the number of directories in the PATH.

`echo $PATH | tr ':' '\n'´ | wc -l `
### 4. Global variables
Create a script that lists environment variables.

`printenv`

printenv - prints all or part of the environment
### 5. Local variables
Create a script that lists all local variables and environment variables, and functions.

`set`

lists all local variables and environment variables, and functions in linux

### 6. Local variable
Create a script that creates a new local variable.

Name: BEST
Value: School

`export BEST="School"`
### 7. Global variable
Create a script that creates a new global variable.

Name: BEST
Value: School

`export BEST='School'`
### 8. Every addition to true knowledge is an addition to human power
Write a script that prints the result of the addition of 128 with the value stored in the environment variable TRUEKNOWLEDGE, followed by a new line.

`echo $((128 + TRUEKNOWLEDGE))`

**$(( ))** Arithmetic expansion — Comparable to the above, but the expression is replaced with the result of its arithmetic evaluation. Example: echo "The average is $(( (a+b)/2 ))"
### 9 Divide and rule.
Write a script that prints the result of POWER divided by DIVIDE, followed by a new line.

POWER and DIVIDE are environment variables

`echo $((POWER / DIVIDE))`
### 10. Love is anterior to life, posterior to death, initial of creation, and the exponent of breath
Write a script that displays the result of BREATH to the power LOVE

BREATH and LOVE are environment variables
The script should display the result, followed by a new line

`echo $((BREATH ** LOVE))`
### 11. There are 10 types of people in the world -- Those who understand binary, and those who don't
Write a script that converts a number from base 2 to base 10.

The number in base 2 is stored in the environment variable BINARY
The script should display the number in base 10, followed by a new line

`echo $((2#BINARY))`
change of base from binary to decimals
BINARY=10100111001
1 x 2^0 = 1 x 1 = 1
0 x 2^1 = 0 x 2 = 0
0 x 2^2 = 0 x 4 = 0
1 x 2^3 = 1 x 8 = 8
1 x 2^4 = 1 x 16 = 16
1 x 2^5 = 1 x 32 = 32
0 x 2^6 = 0 x 64 = 0
0 x 2^7 = 0 x 128 = 0
1 x 2^8 = 1 x 225 = 225
0 x 2^9 = 0 x 512 = 0
1 x 2^10 = 1 x 1024 = 1024

1 + 8 + 16 + 32 + 225 + 1024 = 1337
### 12. Combination
Create a script that prints all possible combinations of two letters, except oo.

Letters are lower cases, from a to z
One combination per line
The output should be alpha ordered, starting with aa
Do not print oo
Your script file should contain maximum 64 characters

`bash -c 'printf "%s\n" {a..z}{a..z}' | grep -v "oo"`
### 13. Floats
Write a script that prints a number with two decimal places, followed by a new line.

The number will be stored in the environment variable NUM.

`printf "%0.2f\n" $NUM`
### 14. Decimal to Hexadecimal
Write a script that converts a number from base 10 to base 16.

The number in base 10 is stored in the environment variable DECIMAL
The script should display the number in base 16, followed by a new line

`printf "%x\n" $DECIMAL`
### 15. Everyone is a proponent of strong encryption
Write a script that encodes and decodes text using the rot13 encryption. Assume ASCII.
`tr 'A-Za-z' 'N-ZA-Mn-za-m'`
### 16. The eggs of the brood need to be an odd number
Write a script that prints every other line from the input, starting with the first line.

`paste -d, | cut -d, -f1`
# 17. I'm an instant star. Just add water and stir.
Write a shell script that adds the two numbers stored in the environment variables WATER and STIR and prints the result.

WATER is in base water
STIR is in base stir.
The result should be in base bestchol
`printf '%o\n' $((5#$(echo $WATER | tr water 01234) + 5#$(echo $STIR | tr stir. 01234))) | tr 01234567 bestchol`
