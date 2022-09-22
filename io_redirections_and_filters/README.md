# Shell, I/O Redirections and filters
input/output redirection functions, commands such as ls print their output on the screen as standard output
### standard output
most programs display their output in a standard output by default, the standard output directs its contents to the screen. to redirect the standard output to a file, the ">" character is used if 

**ls > file.tx**

Writes the results to a file, it does not appear on the screen, each time the above command is repeated, file.txt rewrites the beginning with the command output, to add new results to file, we use ">>" like this 

**ls >> file.txt**
### standard input
by default standard input gets its contents from the keyboard, but like standard output, it can be redirected. to redirect standard input from a file instead of the keyboard, the "<" character is used if: 

**sort < file.txt**

we use sort command to process the contents of file.txt, the results are displayed on the screen as the standard output is not redirected, we can redirect the standard output to another file like this 

# Tasks
### 0. Hello World
Write a script that prints “Hello, World”, followed by a new line to the standard output.

`echo Hello, World`
`echo [option] [string]` 
an entry is entered, and it is received and displayed again unchanged.

### 1. Confused smiley
Write a script that displays a confused smiley "(Ôo)'.

echo "\"(Ôo)'"

`**\** Escape : (backslash) prevents the following character from being interpreted as a special character. This works outside quotation marks, inside double quotation marks, and is generally ignored between single quotation marks.`
### 2. Let's display a file
`cat /etc/passwd`
**cat:** concatenar archivos e imprimir en la salida estándar
`cat [ CHOICE ]... [ FILE ]...`
### 3. What about 2?
Display the content of /etc/passwd and /etc/hosts
`cat /etc/passwd /etc/hosts`
### 4. Last lines of a file
Display the last 10 lines of /etc/passwd
`tail /etc/passwd`
**tail** - generates the last part of the files
### 5. I'd prefer the first ones actually
Display the first 10 lines of /etc/passwd
`head /etc/passwd`
head - generates the first part of the files
### 6. Line #2
Write a script that displays the third line of the file iacta.

The file iacta will be in the working directory

You’re not allowed to use sed
`head -3 iacta | tail -1`
### 7. It is a good file that cuts iron without making a noise
Write a shell script that creates a file named exactly \*\\'"Best School"\'\\*$\?\*\*\*\*\*:) containing the text Best School ending by a new line.
``echo "Best School" > "\*\\\'\"Best School\"\'\\\*$\?\*\*\*\*\*:)`
**\**
### 8. Save current state of directory
Write a script that writes into the file ls_cwd_content the result of the command ls -la. If the file ls_cwd_content already exists, it should be overwritten. If the file ls_cwd_content does not exist, create it.
`ls -la > "ls_cwd_content"`
**ls** - list of directory contents
**-l**(use a long list format) and **ls -a**(do not ignore entries beginning with ).
### 9. Duplicate last line
Write a script that duplicates the last line of the file iacta

The file iacta will be in the working directory
`tail -n 1 iacta >> iacta`
**-n** generate the last NUM lines, instead of the last 10; or use
              -n +NUM to the output starting with the NUM line
### 10. No more javascript
Write a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders.
`find -name "*.js" -type f -delete`
**-name** Base of file name
**type:** displays information about the type of command, we can know what type of element is associated with a given command.
**-f** suprime la búsqueda de función de shell, With this option you will be instructed not to parse commands that are associated with functions.
### 11. Don't just count your directories, make your directories count
Write a script that counts the number of directories and sub-directories in the current directory.

The current and parent directories should not be taken into account
Hidden directories should be counted
`type [<drive>:][<path>]<filename>`
