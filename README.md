## Introduction to Linux Concepts and Commands 
### Some Important Concepts: 

#### Linux Introduction:   
Linux is a combination of kernel and GNU components such as applications, window managers, file structures and so on. A kernel is a program that helps the interaction between computer hardware and computer applications (software).Together they make a linux Operating system.  
  
Linux Distributions all have the same kernel but different gnu components. Some of the popular linux distributions are alpine, ubuntu, fedora and more than 1000 exsists as of today being an open source program it allows different developers to make changes to the gnu components and create their own distributions

**True UNIX vs Unix-Like:**                                                                          
True Unix operating systems are evaluated by some standard rules set by an organization called the open group. For an Os to be true Unix compliant it is evaluted by the open group according the to the standards and once it is compliant it is called as true unix. Macos is an example of true unix. Unix Like Os are not compliant  against the rules/standards set by open group hence called unix like they are mostly open source. e.g alpine,ubuntu,fedora

**Linux Terminal:**  
Terminal is a software that comes with the operating system which allows us to communicate to shell which in result communicates to operating system and displays any results based on the input we provided via terminal

**Linux Shell:**  
Shell is a program that exposes a computer os to the one who is controlling it. It allows one to interact with the operating system to perform operations on the operating system


**Types of Commands:**
There are basically four type of commands:  
- An executable program usually stored in /bin  /usr/bin or usr/local/bin. These are compile binary files hence bin
- A built in shell command. Commands part of shell
- A shell function
- An alias  is custom user command

We can find the types of commands using type and then followed by command


=====================================================================  

#### The basic structure of a commands is:

**command -options arguments**

-----------------------------------
  
**Arguments:**
something that we can give as an input to a command.
<pre> i.e echo "hello world" . Here "hello world" is an argument to command echo. </pre>
  
some commands might take more than one argument such as ncal july 2023. it takes july and 2023 as arguments.    
Commands use take arguments in the format they expect. I.e we cannot pass month after year so we need to be vary of that.
  
we can use arguments with commands as most commands use arguments.i.e 
<pre>echo hello   : here hello is an argument to echo command
ncal 2021    : here 2021 is an arument to ncal command. It will print whole 20201 calendar.

It's not necessary that it will always accept one argument. some commands require more arguments.
The order of arguments also matters in some commands but not necessarily in all of them.
</pre>
---------------------------------
**Options:**  
Most of the commands in linux support options. options are generally specified with a dash and some alphabet or a word. ncal -h . options can be combined ncal -3 -h or ncal -3h  

options change the behaviour of commands. i.e  
<pre>
ncal -j		 : will print current month with days in 1,2,3 format. i.e it will print the day according to 365 days and will highlight which day of the
                  year it is.
ncal -h		 : will print the current month without highlighting the current day.
ncal 2022 -j	 : will print the whole year in 365 days format and highlights the current date

We can combine multiple options: like
ncal -3hMj       : will print the the previous current next month with monday as first day and with no highlighting
</pre>
====================================================================================

### Some of the basic commands:

<pre>
- apt					  : apt stands for advance packaging tool, it can be used with different commands like apt update, apt install etc .
					   it is necessary to update before installing any packages. i.e apt update and then apt install
 
- apt list				  : apt list shows what packages are installed on our ubuntu/linux system

- pwd			                  : present working directory

- ls			                  : list all files/folders in current working directory

- cd dirname		                  : change directory to a particular directory 

- cd ..			                  : to go to previous directory

- touch			                  : touch command is used to create files

- mkdir			                  : make directory

- mv ../fname .		                  : to move a file from previous folder to current working directory

- rm _filename_		                  : to remove a file with name 

- cd ~ or cd		                  : to goto home directory

- sudo			                  : to run any command as administrator

- sudo apt-get update		          : to install any updates on ubuntu or linux

- man				          : man means manual, use with commands to learn more

- apt-get install pckg                    : to install any softwares on ubuntu/linux pckg represents package name

- cp source dest                          : copy file from source to destination

- sudo scp i keyPname source destination  : scp command is used to copy any file from server to local or local to server but it will only be used in local 
                                             server
  e.g sudo scp -i mykeypair.pem downloads/raju.png ubuntu@ec2-54-72-184-240.eu-west-1.compute.amazonaws.com:/home/ubuntu/my_folder
	

- touch file-{1..10}.txt                  : to create multiple files

- rm file-{1..10}.txt                     : to remove multiple files

- rm textfiles*				  : to remove all files with string textfiles. i.e this will remove all files with textfiles as names in current 
                                            directory   

- free					  : free command is used to check hhow much memory is used (Ram)

- top					  : top command is used to check which processes are running in our RAM. 


- df -H					  :  df -H is used to check how much disk is free and how much is utilized

- awk					  : awk is a scripting language used to manipulate files or outputs, used for segmenting outputs i.e we can display 
                                            columns  

- df -H | awk '{print $1}'		  : the output of df -H will be input to awk using pipe(|) and awk will print the first column 


- crontab				   : a file where we see what is being scheduled

- crontab -l				   : to list all the cron jobs in our system

- crontab -e				   : to edit a crontab file


- rm -r directory name                     : to remove directory recursively and all its content

- ls -1                                    : to list files/folder by single line

- mv dir_name new_dir                      : to rename a directory

- mv file_name new_file                    : to rename a file

- mv file_name /home/raju/new_file         : to move file to new directory with a new name

- cat filename				   : to display the content of small file

- less filename				   : to list the contents of long file in an interactive way

- head -5 filename			   : to display the first five lines of a file

- tail -5 filename			   : to display the last five lines of a file

- script filename                          : to recored every command you type and its output and save it in a file. very handy if you keep forgetting 
					     commands you runned in your linux.  

- join file1 file2                         : join two files depending upon the similarity between them

- split filename taggingname               : split larger files into smaller files. default size for smaller size file is 1000 lines. used with flags -n to  					     specify how many small files you want to create of large file  


- diff  file1 file2                        : used to show the difference between two files. used with flags -d to show which lines needed to deleted to make 
                                             the identical, -c the changes to be made in file1 and file2 to make them identical.  

- comm file1 file2                         : used to compare two sorted files. The first column in output shows element only in file1 , second column shows 					     the only element in file2, third line shows common elements.
  

- cmp file1 file2                          : used to compare files. outputs the line number in which there is difference between two files.

- wc filename                              : used to count the words in a file along with spaces. use with flags. i.e -l lines , -w words , -L longest , -m 					     character counts
  

- cut filename                             : used to cut portion of a file. flags -f and -c. -f print only these fields, -c select only these character

- paste file1 file2                        : used to join two files together. it displays in column form. useful to see difference as well

- grep -n apple file1 file2                : used to search out a field in a file or files. -c count of occurences , -l display list of files which contains 
					     keyword/pattern/word, -n display line number along lines containing a pattern.  

- aspell check filename                    : to check a spelling mistake in a word in a file.

- nl filename                              : to list the contents in a file with an index number. useful to write it to another file in with an index 
				             starting from 1

- gpg -c filename                          : to encrypt a file


- nautilus directorypath                   : to open any directory from terminal. i.e nautilus Desktop

- login                                    :    used to login as a different user
	
- passwd                                   :    used to set a password for the current user you are logged in as
</pre>
=============================================================================

Udemy Linux Commands:

======================================================================
### Getting Help in Linux:

Operating System by default comes with some manual pages. Manual pages are helpful in learning about what a command does. It tells us the purpose of a command and how to use it with options and arguments.

**Help commands in linux are:**

- man               : used to print manual of commands i.e thier usage, options and all the info regarding a command

  Syntax: 
    man command
    
  Usage:
    man echo, man less, man grep and so on
 -------------------------------------------------
 
- **type**               :  type commans will tell us the type of a command

  Syntax: 
    type command
    
  Usage:
    type echo, type less, type grep and so on
  
 -------------------------------------------------
 
- **which**               : tells where a command is located. i.e in simple words file name where a command is defined

  Syntax: 
    which command
    
  Usage:
    which echo, which less, which grep and so on
  
 -------------------------------------------------
 
- **help**                : help command used to print out help regarding anything if there is no manual for it.

  Syntax: 
    help command
    
  Usage:
    help echo
    
======================================================================

**Navigation in Linux:**

'/ ' in linux represents the top level or root directory. Every other components are inside this root directory. it contains users, binaries,devices and so on. we can open a root directory on terminal using xdg-open / where / represents root directory. There is an important home directory inside root directory which stores information regarding to the users in the os. home directory is represented as ' ~ ' whereas root as  ' / '

-------------------------------------------------

**Relative vs Absolute Paths:**
Relative path is a path that is related to currently directory you are in. we can use relative paths to navigate between folders. Absolute path is  a path that starts from the root directory that is /  .Absolute path always work as we are referencing the path from root directory whereas relative path might give us some errors if we do not provide the relative path properly

-------------------------------------------------

**Navigation commands in linux are:**

- **pwd**               : used to print the present working directory

  Syntax: 
    pwd 
    
  Usage:
    pwd
  
 -------------------------------------------------   
 
- **ls**               :  used to list the contents of a directory or current path

  Syntax: 
    ls path
    
  Usage:
    ls , ls ~ , ls /
  
 -------------------------------------------------   
 
- **cd**               : used to change directories in linux

  Syntax: 
    cd path
    
  Usage:
    cd ~ , cd / , cd ~/Learning, cd .. 
 -------------------------------------------------   
 
### Overview of Import folders in root directory i.e (/):
- **bin**                : bin contains binaries files for commands
- **etc**                : etc contains configuration files
- **media**              : media contains removeable media like usb, harddisk etc
- **var**                : var contains cache, log and other stuff
- **root**               : root directory is the root folder for super user root. Its not '/'  but root folder inside '/' path. Contains info related to root 
- **usr**                : usr directory contains libs, installed softwares, new commands etc end up there

======================================================================
### Creating Files and Folders in Linux:
Linux terminal provides us several commands to create files and folders. With which we can create files and folders much faster than using gui.

**commands for creating files/folder in linux are:**
- **touch**               : used to create file 

  Syntax: 
    touch filename 
    
  Usage:
    touch hello.txt , touch ~/Learning/linux.txt, touch file{1....100}.txt
  
 -------------------------------------------------   
- **mkdir**               :  used to create directories

  Syntax: 
    mkdir foldername
    
  Usage:
    mkdir test , mkdir ~/Linux , mkdir -p ~/Learning/Devops
  
 -------------------------------------------------   
- **file**               : used to determine a file information 
  Syntax: 
    file filename
    
  Usage:
    file hello.txt , file ~/hello.txt, file pic.png
    
 -------------------------------------------------
  
======================================================================

### Nano Editor in Linux:

-------------------------------------------------
Nano is a command line editor to edit files.  Also it allows to create new files and edit them.There are some other editors such as pico, vim. Nano provides several shortcuts keys that usually start with Ctrl or Alt key on keyboard.

 Syntax: 
    nano filename
    
------------------------------------------------- 
 **Shortcuts:**
 - Ctrl + O used to write out any lines. save lines and keep the editor open
 - Ctrl + X to exit out of nano
 - Ctrl + S to save written lines in a file created using nano
 - Alt + \ or / to move to first and last line in a file or Ctrl + up or down arrow key
 - Ctrl + G to get help regarding nano shortcuts and other stuff
 - Alt + shift + 4 key to fit the content of a large file to make readable
 - nano +15399 country-data.json  allows nano to open  a file at specific line number
 - Ctrl + R is used to insert the content of another file to currently open file

======================================================================
### Copy,Removing,Moving files in Linux:
Linux provides three commands to copy,reomve or move files

**Commands:**
 
- **cp**              : used to copy contents of a file/folder to another file/folder

  Syntax: 
    cp sourcefilename destinationfilename
    cp -r sourcedirectory destinationdirectory
    
  Usage:
    cp file1.txt file2.txt, cp -r ~/Learning/ MyLearning
-------------------------------------------------    
- **rm**               :  used to remove files/directories

  Syntax: 
    rm file1 
    rm -r foldername
  Usage:
    rm file.txt , rm file1.txt file2.txt file3.txt , rm file*, rm -r ~/Linux , rm -d folder , rmdir folder , rm -ri folder
-------------------------------------------------    
- **mv**               : used to mv files/folders to another file/folder
  Syntax: 
    mv sourcefile destinationfile
    mv sourcefolder destinationfolder
  Usage:
    mv file1.txt file2.txt , mv file1 file2 file3 finalfile, mv ~/folder ~/myfolder/, file pic.png
    
======================================================================
### Shorcuts in Linux:

- **ctrl + L** to clear the terminal screen
- **ctrl + a** to move cursor to start
- **ctrl + e** to move cursor to the end
- **ctrl + f** to move forward one character
- **ctrl + b** to move cursor backward one character
- **alt + f** to move cursor one word forward
- **alt + b** to move cursor one word backward
- **ctrl + t** to swap two characters
- **ctrl + k** to clear the text from a cursor point forward
- **ctrl + u** to clear the text from cursor point to backward
- **alt + d** will delete the current work
- **crlt + d** will delete the current character
- **ctrl + y** to restore something delted in command line using ctrl + U or ctrl + k
- **history** to show history of the run commands on terminal. we can use !number to rerun the specific command on that number
- **ctrl+ R** on terminal allows us to search for the command that we run from history

======================================================================
### Working with Files in Linux:

**Commands:**
 
- **less**              : will show the contents of a long file page by page in a more readable way

  Syntax: 
    less filename
    
  Usage:
    less file1.txt , less /var/log/access.log
-------------------------------------------------    
- **head**              :  head will print the first 10 lines of a file. We can specify the lines by using -n flag. i.e head -n 100 filename

  Syntax: 
    head filename 
    
  Usage:
    head mybook.txt, head -n100 mybook.txt
-------------------------------------------------    
- **cat**               : used to print the contents of a file or concatenate the contents of file

  Syntax: 
    cat filename
    cat file1 file2 
    
  Usage:
    cat countries.txt, cat birds.txt mamals.txt   
-------------------------------------------------    
- **tac**              : reverses the output of cat. i.e prints last line first and so on

  Syntax: 
    tac filename
    tac file1 file2
    
  Usage:
    cat countries.txt, cat birds.txt mamals.txt animals.txt   
-------------------------------------------------
- **rev**              : rev  reverses the characters inside a file. i.e cat will be tac

  Syntax: 
    rev filename
    rev file1 file2 
    
  Usage:
    cat countries.txt, cat birds.txt mamals.txt 
-------------------------------------------------    
- **tail**             : prints the last 10 lines of a file. tail -f is used to print following lines when occur.useful when dealing with logs

  Syntax: 
    tail filename
    
  Usage:
    tail /var/log/nginx.log , tail -f /var/log/nginx.log 
    
-------------------------------------------------    
- **wc**              : used to print word count or lines in a file

  Syntax: 
    wc filename 
    
  Usage:
    wc countries.txt, wc -w countries.txt, wc -l countries.txt   
-------------------------------------------------    
- **sort**             :   to sort out the contents of a file alphabetically or numerically. important flags are -u for unique,-n for numeric,-r for reverse sort

  Syntax: 
    sort filename
    
  Usage:
    sort countries.txt, sort -u countries.txt, sort -r countries.txt   

======================================================================

### Redirection and Standard Streams in Linux:

-------------------------------------------------
Redirection is a process of pointing an input or output to another input or output or to some file.

By default there are three standard streams in linux which are standard input, standard output and standard error. Each of them are represented in numerically as 0, 1, and 2 respectively.

-------------------------------------------------
**Standard Output:**
Standard output is a place to which a program or command can send information. The info could go to a screen, file or a printer or to another command. The redirection symbol for an standard output is ' > ' or '1>'   e.g when we use an ls command in a terminal it gives output on the terminal screen but we can redirect it to a file using standard output stream i.e ls > list.txt and so can be the case for other commands

-------------------------------------------------
**Standard Error:**
Standard Error is a place where commands and programs sends error information to. The redirection symbol for the standard error is ' 2> ' . when we use an invalid command or option on terminal it shows error on the terminal but we can redirect that to a file or printer. i.e what is not a linux command we can redirect it to a file called error.txt like this what 2> error.txt

-------------------------------------------------
**Standard Input:**
Standard input is where a command or program get its information from. by default the shell directs standard input from the keyboard but it can come from a file or another command. The redirection symbol for a standard input is  ' < ' or ' 0< '. We can input a file to standard input as cat < list.txt. By default some commands in linux are opted to listen in for standard input when no option or argument is provided. just like cat command

-------------------------------------------------
We can append a stdout to a file as well using >> symbols. We can redirect a standard input to a standard output. i.e cat < words.txt > anotherfile.txt . Stdout and stderror can work together as well. i.e ls > list.txt 2> error.txt 

-------------------------------------------------
We can also use some fancy shortcuts for this for redirecting stdout and stderror to same file.     ls > list.text 2>&1 . Also we can use ls &> list.txt this will redirect both stdout and stderror to same file.

-------------------------------------------------
======================================================================
### Piping in Linux:
Piping in linux is a term used to pass output of a command as an input to  another command.  It is represented as ' | ' symbol. Example is date | rev
Difference between piping and redirection is that in redirection we redirect an output of a command to a file usually. But with piping we pass the output of a command to another command as an input. We can do multiple piping of commands

-------------------------------------------------
Usage:
- ls | less
- ls -l /usr/bin | less
- cat book.txt | less
- ls -1 | wc -l
- cat -n countries.txt | head -n 20 | tail -n10
------------------------------------------------- 

- **tr**             : used to truncate or replace a word/character with another word/character.  useful command when used with piping. Important flags -s and -d 

  Syntax: 
    tr 'word/charcter' 'word/character'
    
  Usage:
    echo text | tr x s , tr 'r' 'b' < file1, echo raju | tr a-z A-Z, cat phone.txt | tr -d [:alpha:] | tr -d : | tr -d +
-------------------------------------------------
- **tee**             : tee command reads standard input and copies it to both standard output and file.

  Syntax: 
     tee [OPTION]... [FILE]...
    
  Usage:
    echo hello | tee hello.txt | cat  , cat countries1.txt countries2.txt | tee country.txt | wc -l


======================================================================

Expansion in Linux:

-------------------------------------------------
Expansions are of several types in linux.  Pathname expansion, tilde expansion, arithmetic expansion
Pathname extension uses several symbols which have their meaning. characters/symbols such as *, [], $. We can use special wildcard characters to build patterns that can match multiple files at once.

-------------------------------------------------
The asterik ( * ) character represents zero or more characters in a filename. e.g ls *.css , cat blue* will match every file with a css extension and every file starting with blue word respectively.  another example can be echo *file* will match that has file word in it

-------------------------------------------------
The question mark ( ? )  character reprsents any single character.        e.g  ls app.?? will match any file with two extension having two characters  app.js , app.py etc      ls pic?.png will result in pic2, pic1, or any picA.png files if present in current directory

-------------------------------------------------
The [] characters can be used to match a range of characters. eg. ls pic[123].png  will only match pic1.png, pic2.png and pic3.png ls [A-F]* will match any files or folder starting with letters from A to F. ls pic[1-9].png will list pic1 to pic9

-------------------------------------------------
Remember with these characters we can not only use ls or echo, we can use cp, mv, rm which is useful with these commands and any command that takes files as an argument or standard input we can use it. Also these symbols can be used with each other to create more complex patterns for our use cases. 

-------------------------------------------------
Negating ranges : inside of square [] brackets we can specify a range of characters not to match using symbol caret ( ^ ) . E.g ls [^a]* will match any files that do not start with character a. ls [ ^0-9]* will match any files that do not start with a numeric digit. echo [^Cc] to not match any files with upper C or lower c

-------------------------------------------------
Tilde ( ~ ) is expanded to home directory of the current user. when we do cd ~ it redirects us to our current user home directory.

-------------------------------------------------
Brace Expansion basically generates multiple strings for us based on a pattern. we provide set of strings inside curly braces { } as well as surrounding suffixes and prefixes . e.g touch file{1,2,3}.txt will generate  file1,file2,file3 altogether. Useful when creating files and folders faster. We can also create nested brace expression echo {A,{a..z},Z}

-------------------------------------------------
Arithmetic expansion can be done in terminal. Shell does it using $((expression)) e.g echo $((5%3))

-------------------------------------------------
Command substitution in linux is done using $(command)

-------------------------------------------------

======================================================================
### Finding things in Linux:
The following commands are useful when looking for a file in linux or try to find files depending upon folder locations etc.

-------------------------------------------------
- **locate**             : performs a search of pathnames across our machine that matches a given substring and prints out any matching names

  Syntax: 
    locate string
    
  Usage:
    locate hello.txt, locate myfile
 -------------------------------------------------
    
- **find**             : find is another command that is used to locate files/directories inside linux. it is more powerful than locate as it doesn't uses a
                     database. find works with relative path. when we write find it list all the directories and files in current directory as well as 
                     the contents in the sub directories. But we can use absolute paths with find command to locate for files inside a specific directory.   Syntax: 
    find string/filename
    
  Usage:
    - find -type f  is used to locate only files in current directory and subdirectories e.g find ./ -type f  , find ~ -type f
    - find -type d will list all directories and sub directories in current folder e.g find ./ -type d , find ~ -type d
    - we can provide a specific pattern for find to use when matching filenames and directories with the -name option we need to enclose our pattern in "".
      e.g to find all files in my current directory that end with .txt extension i can use: find -name "*.txt", find ./ -name "*.ht??"
    - find ~ -name "Poke" will look for exact file in our home directory that has Poke in it either it be file or directory
    - find ~ -name "*Poke*" will look for any files/folder that has Poke in it so we can use steric expansion within find to look for files but this is
      case sensitive so if there is any poke it will not list it.
    - find ~ -iname "*Poke*" will list any file/folder that has Poke or poke in it
    - find -size  will help us find files by  size. with -size we can use plus or minus simbol. Plus means any file greater and minus means any file less.
      e.g   file -size +1G will look for any files greater than 1Gb in current directory. file -size -10MB will look for any files less than 10MB in current 
      directory
    - find -user raju will look for files with user raju
 -------------------------------------------------   
    
Timestamps are of three types in general in linux.  modification time(mtime), change time (ctime) and access time (atime).  modification time is a time which shows when a file was last modified or its contents were changed.  change time is when a file was last changed , this occurs whenever an mtime changes, also when we rename or move a file or alter its permission. access time is when a file is read by an application or a command like cat or less

-------------------------------------------------
echo "hello" >> hello.txt will create a file with name hello.txt when we will use ls -l we can see the modified time. ls -lc will help us to see the file changed time. but as we have created the file so mtime and ctime will be same to test ctime we can mv file to hellow.txt and now when we will do ls -lc it will show change time. to see accesstime we can use ls -lu. to update access time we can use cat or less command and access time will be updated.

-------------------------------------------------
- find -mmin +30 to look for files that were modified more than thirty minutes ago. similarly atime and ctime will be for access and change minimum time
- find -atime +1 to look for files that were accessed 1 day ago. it works in 24 hours format. similary ctime and mtime can be used
-------------------------------------------------
find can also be used with the logical operators i.e and, not , or. for not we can also use ! instead of writing not.

- find -type f -not -name "*.txt"
- find -type f -and -name "*.txt" 
- find -type f -or  -name "*.txt"
-------------------------------------------------
We can use find with exec option to perform any actions on the matches like copy, remove, list etc.  by default some commands do not accept the stdouput  redirected to any other command standard input via pipe so to perform this action we have to use  the -exec option with the find command. but we need to use {} and ; in the single quotes . {} matches every file and ; represents end of line. 
Usage
- find -type f -and -empty -exec ls -l '{}' ';'
- find -type f -and -empty -exec rm -ri '{}' ';'
-------------------------------------------------
By defualt some commands do not accept the stdinput that comes via a pipe e.g find -empty | ls -l .  but for that we can use exec option with find as mention aboved but what happens is it runs the command for each match file i.e if there are four files in current directory it will run the ls command for each of them one by one. There is another command which we can use to pass the output of find to ls or other command that do not accept standard input via a pipe. The command is xargs. The xargs command passess the output of a command as stdin as arguments not one by one.  e.g find -empty | xargs ls -l
- echo file file2 | xargs touch will create two files file and file2
- echo dir1 dir2 | xargs mkdir will create two directories



======================================================================
### Grep Command:
The grep command searches for a pattern in each file's content. Grep will print each line that matches a pattern we provide.Grep is case sensitive
  Syntax: 
     grep pattern filename
    
  Usage:
    grep "chicken" animals.txt

-------------------------------------------------
**Important options:** 
-w for exact word, -i for case insenstive, -r for recursive, c for count , n for numbering the lines on which there is occurence of the pattern, A1 for line after the match, B1 for line before the match, C1 will print line after and before the match, m option to limit the options of occurence, i.e m1 will give first match

- grep -w "cat" book.txt  will only look for a word cat in book.txt file
- grep -i "aus" countries.txt  to get case insenstive lines that contain the word aus
-------------------------------------------------
Using grep we can do a recursive search  using a -r option which will include all files under a directory, subdirectories and files and so on. if we don't specify a starting directory it will search the current working directory. grep -r "aus" will search in current directory in all files , sub folders for the occurence of "aus"

- grep -ri "aus"
- grep "grass" SongOfMyself.txt -i -w -B1 -A1  or  we can use grep "grass" SongOfMyself.txt -i -C1
- grep "grass" SongOfMyself.txt -ic
- grep "6" SongOfMyself.txt -wn to find the exact line on which 6 occurs in the file
- grep "grass" SongOfMyself.txt -m2

-------------------------------------------------
We can provide regular expression to grep command in pattern. Regular expressions help us match complex patterns.  in case of grep there are symbols which have specific meanings to it.

-------------------------------------------------
dot ( . )  matches any single character. e.g  grep "r.." SongOfMyself.txt  matches any word that starts with r and and has two or more characters in it for exactly two character after r we can use it with -w flag. e.g grep "r.." SongOfMyself.txt -w

-------------------------------------------------
Power ( ^ ) matches any start of the line. e.g grep "^r" SongOfMyself.txt -i

-------------------------------------------------
Dollar ( $ ) matches any end of the line . e.g grep ")$" SongOfMyself.txt        or    grep ",$" SongOfMyself.txt

-------------------------------------------------
[abc] matches any character in the set. e.g grep "[abc]" SongOfMyself.txt -w or we can use with '.' for better searching: e.g grep "[abc].." SongOfMyself.txt -w     or grep "r[abc]" SongOfMyself.txt 

-------------------------------------------------
[^abc] match any character not in the set . eg. grep "[^abc]" SongOfMyself.txt -w

-------------------------------------------------

[A-Z] matches characters in range . e.g grep "2[1-6]" SongOfMyself.txt  or grep "2[^1-6]" SongOfMyself.txt 
or grep "r[a-c]" SongOfMyself.txt

-------------------------------------------------
Simple grep will ignore some the special characters but we can use extended grep  to use special character such as ?. + and so on.  egrep "birds?" SongOfMyself.txt or grep "birds?" -E  SongOfMyself.txt  . The -E flag tells that the s before ? is optional

-------------------------------------------------

grep -E "[aeiou]{2}" SongOfMyself.txt here {2} tells that two voewels with each other

Grep can be used with other commands using Pipes and is most useful.

-------------------------------------------------
find ~/Learning/Linux/ -type f | xargs grep gatsby


======================================================================

### Permissions in Linux:
Linux is a multi user OS. Means there can be multiple users on a single OS who can have the access to resources and apps. We can setup users and set permissions for the users for accessing files and directories. In linux we can create users and groups for setting permissions on the files/folders.  We can assign multiple users to a group and thus set permission for accessing files/directories depending upon user and group. To list the permission of a directory we can use ls -l $HOME

-------------------------------------------------
When we do ls -l on a directory it list the contents of a directory and shows the output in a columns. The first columns reprsents permissions characters consisting of 10 chars where each character has a specific meaning. The second column represents no. of hard link to a folder/file. The 3rd column shows the user name, 4th column shows group name, 5th column shows size, 6th column shows modification time, 7th column shows file/foldername.

-------------------------------------------------
There are 5 characters used in first column: -  d r w x  each having their own meanings. These characters are used together for setting permission on a file/folder

- d  defines that the following is a  directory.
- '-'   represents regular file
- r  :  read only
- w : write only
- x :  execute only
-------------------------------------------------
The ten characters we see when we do ls -l on a path  are called file attributes 
d r w x r w x r w x
- r w x r w x r w x

and have specific meaning.
The 1st ( d/-/l/c/b ) character represents either if its a directory or a file. d represents its a directory and - a regular file. The next 3 (r,w,x) characters represents user permission on that file/folder, The next 3 (r,w,x) characters reprsents group permission on that file/folder, and the last 3 (r,w,x) characters represents world/all/others permission on that file/folder

======================================================================
### Altering Permissions:
To change the permission of a file/folder we can use change mode i.e chmod command . to use chmod to alter permission we need to tell it. who we are changing permission for  what changes are we making, adding or removing permissions of a user  and which permissions are we setting

-------------------------------------------------
Syntax:
  chmod mode filename
  chmod -r mode foldername
  
When specifiying permission with chmod , we use a special syntax to write permission statements. First we specify the "who"  with following values. 
- u for user
- g for group 
- o for others(world) and a for all of the above
-------------------------------------------------
Next we tell chmod "what" we are doing using the following characters: 
 - Plus (+) for granting permissions
 - Minus (-) for removing permissions 
 - Equals (=) sets a permission and removes others
-------------------------------------------------
Finally, the "which" values are:
- r for read permission
- w for write
- x for execute permission
-------------------------------------------------
Example Usage:
- chmod g+w file  will give group members write permission to the file.
- chmod a-w file will remove write permission for all the users,groups and world
- chmod u+x file will add execture permission for user group
- chmod a=r file will only add read permission for all (user,group,world)  and remove pervious permissions that was set for the file
- chmod ugo+rwx file is same as chmod a=rwx file as its gives all permission to all users,groups,and others

-------------------------------------------------
Chmod actually uses two types of notations. symbolic as we saw above and there is another notation called octal notation.

**The octal representation starts from 0 to 7 ( 0,1,2,3,4,5,6,7,8). The binary representation of all these number is different and we can use it to change the permission of a file and folder.**

-------------------------------------------------
0     0 0 0     - - -  
1     0 0 1     - - x 
2     0 1 0     - w -  
3     0 1 1     - r x  
4     1 0 0     r - -  
5     1 0 1     r - x 
6     1 1 0     r w - 
7     1 1 1     r w x

-------------------------------------------------
Example usage:
- chmod 700 file mean rwx permission for user, no permission for group and no permission for others
- chmod 400 file means only ready permission for user, and no permission for others, and group
-------------------------------------------------

The su command is used to switch user. e.g if I have two users named raju and muneer on my machine. I can switch to other user from terminal using su - muneer. The " - " symbol is short form for --login with su command. The difference between su muneer and su - muneer is that su - muneer changes the current home directory to changed user while only su muneer changes user to muneer and doesn't changes home directory to muneer

-------------------------------------------------
By default there is a super user in linux called root user. The root user has every privilige and access to any files/folders. Means we can install any package, remove or add files to folders and so on

-------------------------------------------------
The sudo command is used to run commands as super user or root user. By default admin users do not have access to all the resources sudo commands allows us to run commands as root users hence giving us access to resources and files. We can check the permitted commands for an individual user using "sudo -l"  command 

-------------------------------------------------
sudo apt update ,sudo chown raju:raju file.txt, sudo apt remove nginx

-------------------------------------------------
We can change the ownership of a file/folder using a command called chown. chown allows us to change file/folder users, groups and others.

-------------------------------------------------
chown raju file.txt to change user
chown :raju file.txt to change group
chown raju:raju file to change both

-------------------------------------------------
Groups in linux are used to grant permission based on the users added to that group and permission attached to that group. we can check a user's groups using groups username command

-------------------------------------------------
To create groups we can use addgroup groupname command
To add users to a group we can use adduser username groupname

-------------------------------------------------

======================================================================
The Environment:
The shell maintains a set of information during a shell session know as environment. It is a just a series of key-value pairs that define properties like user home directory, working directory, name of the shell and so on and for each user these are different. All the environment variables are defined in upper case.

- printenv  to print the env variables for a logged user
-------------------------------------------------
parameter expansion is type of expension where when we type the name of an environment variable shell replaces it with its actual value. e.g echo $USER

-------------------------------------------------
We can define variables in shell using key=value pairs but the are only available in the current shell session.  when we open a new terminal session we cannot use them.  Environment variables are global variables and can be accessed over different shell sessions we can create environment variables using export command. But the env variable we create using export will not be available in a new shell session it will exsist in our current shell and in a child shell if we create using bash command.
- export name=raju will create an environment variable with name=raju

-------------------------------------------------
When we log in, the shell reads info from startup files , first the shell reads from global config files that effect the environment for all the users , then shell reads the config files for each specific user.  The specific files the shell reads from depends upon the type of session. login vs non-login shell sessions.

-------------------------------------------------
for login sessions.  /etc/profile - global config file for all users  ~/.bash_profile - user personal config file .    ~/.bash_login - read if  .bash_profile file isn't found. and ~/.profile - used when both the above personal config files not found

-------------------------------------------------
for non-login sessions.  etc/bash.bashrc - global config for all users. ~/.bashrc - specific settings for each user where we can define our own configurations

-------------------------------------------------
To make our environment variables permanent we can use the .bashrc file located at home directory of our user. so if i add name=raju in .bashrc file it is saved for every terminal session I open.

-------------------------------------------------
We can define our own commands using alias keyword. e.g alias ll=ls -al. If we run then in our command terminal session they will work but to make them permanent we need to put them in .bashrc file

-------------------------------------------------
alias ..="cd .." will create a command ".." which we can use inplace of cd ..




======================================================================
### Writing our own commands:

-------------------------------------------------
We can write shell scripts in linux by creating files. When we create a shell script we define a top line which usually starts with #! which is called shebang. it actually tells the OS which interpreter to use when running/parsing this script. #!/bin/bash tells the OS to use bash interpreter.

-------------------------------------------------
When we write a shell builtin command such as echo or pwd or any other command, the shell looks for executeable typed command program in the list of directories stored in the PATH variable. It starts looking in the first location and then keeps looking until it finds its path.

-------------------------------------------------
echo $PATH gives us the path variable that actually stores the executable program for every command we run in our terminal.
which echo  or whereis echo  will give us the path  where is echo defined in our OS and the path for echo and all other commands is stored in $PATH variable and thats how it was able to run it

-------------------------------------------------

To define our own command we could put the script that we wrote in any of the folders that echo $PATH variable shows but instead we can create a bin directory in our $HOME directory as ubuntu has prebuilt file .profile that looks for any folder in $HOME and if we place any file  in $HOME/bin directory and treats them as a command. e.g when I write a script that says echo and place it under $HOME/bin directory and has properly defined the interperter for it it will execute without any errors.

-------------------------------------------------

It is not neccessary that we only need to put shell scripts inside our $HOME/bin directory we can put other scripts such as python, ruby, go as long as we have the languages installed on our machine and we have properly defined a shebang on top of the script so that the interpreter could know which programming language to use but by default it will try to use bash

-------------------------------------------------


======================================================================
### Cron in Linux:
Cron allows us to schedule commands to run at regular intervals like:  30 minutes of every hour, every two minute , once in a year and so on

To setup a cron job we can use crontab -e  command.


We can use this website to setup a cronjob syntax. https://crontab.guru/



======================================================================
### Process Related Commands:
 - **ps**             : command to display the characteristics of processes

   Usage:
     ps -f        : will show a full listing of all the processes
     ps -u user   : will show a listing of processes run by user
     ps -a        : processes of all users
     ps -e        : processess including user and system

   ps -fu raju    : will list all processing run by raju in full listing mode
    
