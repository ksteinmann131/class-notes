# Command Line Basics

- cd : changes the current directory
- cd ~ : takes you back to the user directory
- cd .. : goes back to the last directory (one step back)
___

- ls : lists whats in current directory (files and other directories)
- -a : all
- -l : long
___

- rm : removes
- f : force
- r : recursive
  - BE CAREFUL! this deletes thing permanently
___

- pwd : (print working directory) gives you the absolute path to where you are now
___

- mkdir : makes new directory
- touch : makes new file
  - .js, .html, .css, .md - denotes what type of file it is
___

- mv (old file name) (new file name) : moves a file (aka renames it)
___

- ctrl c : stops whatever is running (ex. server)
___
- cat : concatenates a file into a string
___

- echo >> : writes to a file
  - goes to the last position in a file and drops some string there
  ex. echo >> .gitignore "some string"
___

- history : shows last 500 commands
___

- grep : searches plain text data sets for lines that match a regular expression
  - Globally search a Regular Expression and Print
  - used to search text or searches the given file for lines containing a mach to the given string of words
    - by default, displays the matching lines
  - use grep to search for lines of text that match one or many regular expressions and outputs only the matching lines
___

#### Move an image.jpg into root directory

Can save an image directly into our root(project) directory so that we don't have to pull the image with a link...
- save the image into Downloads folder in .jpg format
- in command line, first make sure image exists in Downloads
- cd into root directory that we want image to be in
- $ mv ~/Downloads/whatever.jpg .
  - this calls the move function, then points to the user directory (~), then the Downloads directory, then the image(.jpg) file itself

Can then reference the .jpg file directly in the project as it exist in the project directory.
___

##### npm
**n**ode
**p**ackage
**m**anager

##### apm
**a**tom
**p**ackage
**m**anager
