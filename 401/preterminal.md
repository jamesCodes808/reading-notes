# Pre: Terminal

## The Command Line

- What is it?

It is a text based interface to your system. It takes in commands and gives you feedback or performs actions based on the commands. These commands are the command line equivalent to a GUI when accessing or editing files and directories. 

- Basic Navigation

There are a few commands that allow you to traverse directories in the terminal. Some very useful ones to remember are:

pwd - print working directory, current location
<br>
ls - list of files in current directory
<br>
cd pathname - changes directory to the specified pathname
<br>
cd .. - goes up/backwards in directory
<br>
tree - displays file structure

- Manual Pages

If you ever need an explanation of what any of the linux commands do there is a manual page for that. In order to access it and some other useful commands just do the following:

man <command> - Look up the manual page for a particular command.
<br>
man -k <search term> -Do a keyword search for all manual pages containing the given search term.
<br>
/<term> - Within a manual page, perform a search for 'term'
<br>
n - After performing a search within a manual page, select the next found item.

- File Manipulation

Everything in the terminal is either a directory or a file so some of the most useful commands other than navigation commmands are the commands on file manipulation.

Here are some helpful commands:

mkdir pathname - this creates a directory
<br>
touch filename.type - this creates a file with the specified file type
<br>
rm -rf pathname - a recursive and forced way to delete directory and everything in it
<br>
mv filename.type newfilename.type - moves a file or renames it depending on if you specify a directory after the first filename argument

- Final thoughts

The terminal is an invaluable tool and resource that every developer should learn and get comfortable with. It is the equivalent to a dev of a mechanic going under the hood of a vehicle, you can see the inside of these directories and paths and configure, install, remove, edit and update the things inside.

> Reference
>
>[Ryans tutorials](https://ryanstutorials.net/)
>
>[Cheat Sheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)