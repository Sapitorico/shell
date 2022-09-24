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
show the first 3 lines of the last file
### 7. It is a good file that cuts iron without making a noise
Write a shell script that creates a file named exactly \*\\'"Best School"\'\\*$\?\*\*\*\*\*:) containing the text Best School ending by a new line.
``echo "Best School" > "\*\\\'\"Best School\"\'\\\*$\?\*\*\*\*\*:)`
**\** avoids the meaning of the character species
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
 **-n +NUM** to the output starting with the NUM line
 **>>** redirect output to the file without subscribing the content
### 10. No more javascript
Write a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders.
`find -name "*.js" -type f -delete`
**find** - search for files in a directory hierarchy
**-name** Base of file name
**type:** displays information about the type of command, we can know what type of element is associated with a given command.--File is of **-f**  regular file
**-f** suppresses shell function search, With this option you will be instructed not to parse commands that are associated with functions.
### 11. Don't just count your directories, make your directories count
Write a script that counts the number of directories and sub-directories in the current directory.

The current and parent directories should not be taken into account
Hidden directories should be counted
`type [<drive>:][<path>]<filename>`
`find . -type d ! -path . | wc -l`
-d directory
**find** - search for files in a directory hierarchy
**-d** type direcory
**path:** is the address of a file or directory in a file system (i.e., the hierarchy of directories and files used to organize the information stored on a computer). A relative path is an address relative to the current directory (i.e., the directory in which a user is currently working). An absolute path (also called a full path) is an address relative to the root directory (i.e., the directory at the top of the file system and containing all other directories and files).
**wc** print newline, word, and byte counts for each file **-l, --lines**
       print the newline counts
### 12. What’s new
Create a script that displays the 10 newest files in the current directory.

Requirements:

One file per line
Sorted from the newest to the oldest
`ls -1t | head -10`
**ls** - list directory contents
**-1t**  list one file per line, sort by time, newest first; see --time
### 13. Being unique is better than being perfect
Create a script that takes a list of words as input and prints only words that appear exactly once.

Input format: One line, one word
Output format: One line, one word
Words should be sorted
`sort | uniq -u`: Sort without argument requests that the input sort and channel to single printing single words
**sort* - sort lines of text files
**uniq**- report or omit repeated lines
**-u**, **--unique** only print unique lines
### 14. It must be in that file
Display lines containing the pattern “root” from the file /etc/passwd
grep "root" /etc/passwd
`grep root /etc/passwd`
**grep** print lines that match a "root" pattern
### 15. Count that word
Display the number of lines that contain the pattern “bin” in the file /etc/passwd
`grep -c bin /etc/passwd`
**-c, --count** Suppress normal output; instead print a count of matching lines for each input file.
### 16. What's next?
Display lines containing the pattern “root” and 3 lines after them in the file /etc/passwd.
`grep -A 3 root /etc/passwd`
-A NUM, --after-context=NUM Print NUM lines of trailing context after matching  lines.
### 17. I hate bins
Display all the lines in the file /etc/passwd that do not contain the pattern “bin”.
`grep -v bin /etc/passwd`
-v, --invert-match Invert the sense of matching, to select non-matching lines.
### 18. Letters only please
Display all lines of the file /etc/ssh/sshd_config starting with a letter.

include capital letters as well
`grep '^[a-zA-Z]' /etc/ssh/sshd_config`
**[:alpha:]** all letters
### 19. A to Z
Replace all characters A and c from input to Z and e respectively.
`tr [A -Z] | tr [c -e]`
**tr**  translate or delete characters
### 20. Without C, you would live in hiago
Create a script that removes all letters c and C from input.
`tr -d 'c' | tr -d 'C'`
**-d, --delete** delete characters in SET1, do not translate
### 21. esreveR
Write a script that reverse its input.
`rev`
**rev** reverse lines of a file or files
### 22. DJ Cut Killer
Write a script that displays all users and their home directories, sorted by users.

Based on the the /etc/passwd file
`cut -d : -f 1,6 /etc/passwd | sort`
**-d, --delimiter=DELIM** use DELIM instead of TAB for field delimiter **-f, --fields=LIST** select only these fields;  also print any line that contains no delimiter character, -f1,6 for columns (fields) 1 and 6.
### 23. Empty casks make the most noise
Write a command that finds all empty files and directories in the current directory and all sub-directories.

Only the names of the files and directories should be displayed (not the entire path)
Hidden files should be listed
One file name per line
The listing should end with a new line
You are not allowed to use basename, grep, egrep, fgrep or rgrep
`find -empty | rev | cut -d '/' -f1 | rev`
**-empty** File is empty and is either a regular file or a directory. reverses the directories by delimiting the directories in column 1
### 24. A gif is worth ten thousand words
Write a script that lists all the files with a .gif extension in the current directory and all its sub-directories.

Hidden files should be listed
Only regular files (not directories) should be listed
The names of the files should be displayed without their extensions
The files should be sorted by byte values, but case-insensitive (file aaa should be listed before file bbb, file .b should be listed before file a, and file Rona should be listed after file jay)
One file name per line
The listing should end with a new line
You are not allowed to use basename, grep, egrep, fgrep or rgrep
`find -type f -name "*.gif" -printf "%f\n" | rev | cut -d. -f2- | rev | sort -Vf`
**printf** print format on the standard output, interpreting `\' escapes  and  `%'  directives, %f files \n newlines delimited in colum 2 revert and sorted in  natural sort numbers within text and fold lower case to upper case characters.
### 25. Acrostic
An acrostic is a poem (or other form of writing) in which the first letter (or syllable, or word) of each line (or paragraph, or other recurring feature in the text) spells out a word, message or the alphabet. The word comes from the French acrostiche from post-classical Latin acrostichis). As a form of constrained writing, an acrostic can be used as a mnemonic device to aid memory retrieval. Read more.

Create a script that decodes acrostics that use the first letter of each line.

The ‘decoded’ message has to end with a new line
You are not allowed to use grep, egrep, fgrep or rgrep
`cut -c 1 | paste -s -d ''`
**-c, --characters=LIST** select only these characters, **-c**merge lines of files **-s** paste one file at a time and **-d ** reuse characters from LIST instead of TABs
### 26. The biggest fan
Write a script that parses web servers logs in TSV format as input and displays the 11 hosts or IP addresses which did the most requests.

Order by number of requests, most active host or IP at the top
You are not allowed to use grep, egrep, fgrep or rgrep
