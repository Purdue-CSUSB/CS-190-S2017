# CS 190: Tools
### January 11, 2017 <!-- .element: class="subtitle" style="text-align: center"-->



# What is CS 190?


- CS 190 was created by USB in 2012.


- Helps incoming CS students by giving them the **tools** they need to succeed:
   - Terminal
   - Shell Configurations
   - Editors and IDEs
   - Debugging
   - Source Control
   - Life Tips!



# Meet Your Instructors


## Jay Hankins
jh@purdue.edu


## Ahad Sagheer
sshageer@purdue.edu


# Quiz <!-- .element: style="text-align: center"-->


## Quiz 1.1
How would you describe your comfort level in CS?

A. less comfortable

B. more comfortable

C. somewhere in between 



# Syllabus


## Schedule
- Wednesdays, 2:30 PM - 3:20 PM
- One week, you will have lecture. The other week, you will have lab *at the same time*.
- Follow your myPurdue "Schedule-at-a-Glance"


## Grading
- Pass / Fail class
- Each lab is checked for completion.
- If you complete all labs, you will get an **A**.
- You should be able to complete most labs in class. 
- If you can't complete your lab in class, email it to your specific lab TAs as soon as possible. 



# Questions?
### Ask anything! <!-- .element: class="subtitle" style="text-align: center"-->



# Lecture 1: 
### Using the `~»terminal`
<!-- .element: class="subtitle" style="text-align: center"-->



```
~ » echo "Why should I learn the terminal?"
"Why should I learn the terminal?"

~ » cat reasons.txt

1. it's dope af
2. it's rewarding af
3. it's fun af

~ » _
```
<!-- .element: class="hljs nohighlight"-->



# Why Learn the Terminal?


## Why Learn the Terminal?
- `(keyboard > mouse) == true`
   - File manipulation can be done in single commands
   - Repeat and automate tedious tasks easily
   - Terminal commands are universal to many operating systems
- It's what the professionals use
- A lot of times it's all you'll have access to
- You're expected to know it!



# What is the terminal, exactly?


## Terminal Basics
- An interface between the user and the computer
   - Has text input and output (using the keyboard and screen)
   - Sometimes called a TTY <span style="font-size: 0.5em; color: #ccc">(a modern teletypewriter)</span>
- Used to run programs
    + Editors, debuggers, interpreters (e.g. vim, Python)
    + Shells!


## Shells
- Most terminals run a shell by default
- A shell is just a program
    + Allows you to interact with the OS
    + Can access the filesystem, read and write files, and execute programs
- Most people use a shell called BASH
    + Developed in the late 1980s by the Free Software Foundation
    + Default shell on many Linux distributions and macOS.


## Environment
- Every program has an environment, including variables such as:
    - Which user is running the program
    - The directory in which the program is running
    - Configuration parameters
    - etc.


## History and Terminology
- UNIX
    - Operating system developed by AT&T at Bell Labs in the 1970s
    - Inspired many similar OSes like Linux, Solaris, BSD, Darwin, etc.



# Structure of Unix Command 

```
~ » command -options arguments

```



# Navigating in the Terminal


## `ls` - list directory contents
```
# list contents of current working directory
~ » ls

# list contents of a certain directory
~ » ls /homes/hankinsj/cs251

# list contents with hidden files
~ » ls -a
```
<!-- .element: class="hljs nohighlight"-->


## `ls` - advanced list commands
```
# list in long format (more details about files_)
~ » ls -l

# list by descending date
~ » ls -t

# you can combine multiple arguments
~ » ls -alt
```
<!-- .element: class="hljs nohighlight"-->


## `cd` - change directory
```
# navigate into a directory
~ » cd <folder_name>
~ » /homes/hankinsj/cs251

# navigate to the parent directory of the current directory
# aka "go up"
~ » cd ..
```
<!-- .element: class="hljs nohighlight"-->


## `cd` - advanced change directory
```
# navigate to the current user's home directory
~ » cd         [or]         ~ » ~

# navigate to the previously accessed directory
# aka "go back"
~ » cd -
```
<!-- .element: class="hljs nohighlight"-->


## `pwd` - print working directory
```
# print the current directory
~ » pwd
/homes/hankinsj/cs251
```
<!-- .element: class="hljs nohighlight"-->




# Manipulating Files and Folders


## `mv` - move (rename) files
```
# move a file or directory
~ » mv <file_name> </new/location/file_name>
~ » mv <folder_name> </new/location/folder_name>

# rename a file or directory
~ » mv <old_name> <new_name>

# move and rename
~ » mv <old_name> </new/location/new_name>
```
<!-- .element: class="hljs nohighlight"-->
Note:
It may be helpful to mention the structure of a UNIX file system. Sometimes people think that /new/location/ is a command or something. Just clarify with your demo.


## `cp` - copy files and directory
```
# copy (duplicate) a file
~ » cp <file_name> </new/location/file_copy>

# copy a directory
~ » cp -r <folder_name> </new/location/folder_copy>
```
<!-- .element: class="hljs nohighlight"-->
Note:
Make sure to emphasize the -r is for 'recursively'


## `mkdir` - make new directories
```
# make a new folder
~ » mkdir <folder_name>

# make all necessary parent directories as well.
# the folders /cs180/labs/ will be created if they don't exist already.
~ » mkdir -p /homes/hankinsj/cs180/labs/lab01
```
<!-- .element: class="hljs nohighlight"-->



# File Path Tips


## `*` - wildcarding
```
# move all files in /folder/ into /another_folder
~ » mv /folder/* /another_folder/

# copy all files beginning with "cs" into /folder
~ » cp cs* /folder

# remove all files ending in .DS_Store
~ » rm *.DS_Store
```
<!-- .element: class="hljs nohighlight"-->


## `..` & `.` - previous & current directory
```
# .. = one directory up
#  . = current working directory

# navigate to the parent directory of the current working directory
# aka "go up"
~ » cd ..

# move file.txt from the parent directory to the current working directory
~ » mv ../file.txt .
```
<!-- .element: class="hljs nohighlight"-->


## `~` - current user's home directory
```
# navigate to the home directory of the current user
~ » cd ~

# move the folder "project1" into the folder "cs180"
# which is located in the user's home directory
~ » mv -r project1 ~/cs180
```
<!-- .element: class="hljs nohighlight"-->


## `\` - proper space escape
```
# I have a folder named "CS 180 Labs" (with spaces) in my home directory.
~ » cd ~/CS\ 180\ Labs

# or
~ » cd "~/CS 180 Labs"

# or
~ » cd ~/"CS 180 Labs"
```
<!-- .element: class="hljs nohighlight"-->


## A quick note on file extensions
- Used to differentiate file types
  - Can tell you what to *expect* the contents of a file to be.
  - i.e., **.txt** for plain text or **.jpeg** for images
- File are not guaranteed to match their extension
- Files do not have to have extensions



# Connecting to a Purdue Server


## Connecting with a UNIX-like OS
- macOS, GNU/Linux (Ubuntu, Raspbian, etc.)<span style="font-size: 0.5em; color: #ccc">, BSD, Xinu, Darwin, HP-UX, Solaris, Xenix</span>
- Use `ssh`, which is included by default on UNIX-like systems!
- Open your terminal to use `ssh`.


```
~ » ssh <username>@<machine>.cs.purdue.edu

~ » ssh hankinsj@data.cs.purdue.edu
Last login: Mon Jul  4 10:46:19 2016 from rtp-gw1.cisco.com

# hankinsj @ data in ~ [17:17:17]
$ _
```
<!-- .element: class="hljs nohighlight"-->


## Connecting with Windows
- Windows doesn't have `ssh` by default ☹️
- Instead, you need an SSH client, like [PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/).


![PuTTY screenshot](https://raw.githubusercontent.com/Purdue-CSUSB/CS-190-F2016/master/tutorials/shells/putty_screenshots/putty.PNG)<!-- .element: class="center"-->


## Demo



# Wrap Up
- We learned how to:
  + Navigate the terminal
  + Manipulate files and folders
  + Use path shortcuts



# Questions?<!-- .element: style="text-align: center"-->
### Ask anything! <!-- .element: class="subtitle" style="text-align: center"-->



# Quiz <!-- .element: style="text-align: center"-->


## Quiz 1.2
Which command would move all `.txt` files from 2 directories up to my home directory?

A. `mv ../../*.txt ~`

B. `mv ../*.txt ~`

C. `mv /../*.txt ~`

D. `mv ~ ../*.txt`



# Contact Us <!-- .element: style="text-align: center"-->
* cs190-instructors@cs.purdue.edu
* cs190-tas@cs.purdue.edu
