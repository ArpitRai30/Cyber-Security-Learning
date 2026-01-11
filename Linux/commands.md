# Commands
## help
* `help` - 
shows help for shell built-in commands
* `man` - 
opens the full manual for a command
* `tldr` - 
gives short, practical examples of common command usage
## System Commands
* `whoami` - 
username
* `passwd` - 
reset password
* `users` - 
name of all users
* `who` - 
detail of users
* `logout` - 
logout the user
* `halt` - 
bring the system down immediately 
* `init 0` - 
power off the system using predefined scripts (switches system to runlevel 0)
* `init 6` - 
reboots the system (switches system to runlevel 6)
* `poweroff` - 
shuts down the system immediately by powering off
* `shutdown` - 
shuts down the system (can be scheduled and gives warning to logged in users
* `reboot` - 
reboots the system (notifies users)

## File Commands 
* `ls` - 
list files
* `ls -l` - 
list files with more information
    * 1st column - file type and permission
    * 2nd column - number of memory blocks taken by the file or directory
    * 3rd column - owner of the file (user who created the file)
    * 4th column - group of the owner
    * 5th column - file size in bytes
    * 6th column - date and time when file was created or last modified
    * 7th column - represents file or directory name
* `ls *` - 
match 0 or more characters 
* `ls ?` - 
match 1 character
* `ls -a` - 
list files including hidden files
* `ls -lh` - 
list files in human readable form (size in K,M,G)
* `ls -ld /example` - 
list directories
* `ls -lt` - 
list files based on last modified time (recent first)
* `ls -ltr` - 
reverse order of lt (recent last)
* `ls -R` - 
display files recursively
* `ls -F / ls --color=auto` - 
display with colour (directories in blue, soft links in green, and ordinary files in default colour)
* `vi filename` - 
vi editor, if file is present open it else create the file
* `touch filename` - 
if file exists edit its access and modification time to current time else create new file
* `cat filename` - 
display contents of a file
* `cat filename -b` - 
display line numbers in file
* `wc filename1 filename2` - 
word count (totalLines totalWords totalSize(bytes) filename)
* `cp sourceFile destinationFile` - 
copy file (if file is not in present directory then you need to provide complete path)
* `mv sourceFile destinationFile` - 
move file
* `rm file1 file2 file3` - 
remove/delete file (use -i with rm to get a prompt before deletion)
 
## Directory Manangement Commands
* `pwd` - 
print working directory
* `mkdir /path` - 
creates a new directory (creates inside working directory if path is not given)
* `mkdir -p /parent/dir` - 
creates all necessary parent directories in between the path
* `rmdir dirname` - 
removes the directory only if it is empty
* `cd` - 
change directory
* `cd -` - 
go to last directory 
* `mv olddir newdir` - 
move/rename a directory 

## File Permission Commands
(group of rwx - read, write, execute)
(3 types - owner/user(u), group(g), other(o))
* `chmod` - change permissions (symbolic and absolute methods)
  * **Symbolic:**

    ```bash
    chmod o+wx filename 
    chmod u-x filename 
    chmod g=rx filename 
    ```

    * add write and exe permission to other
    * remove exe permission from owner/user
    * give only read and exe permission to group
  * **Absolute:** 

    ```text
    0 : ---
	1 : --x
	2 : -w-
	3 : -wx
	4 : r--
	5 : r-x
	6 : rw-
	7 : rwx
	```

	```bash
	chmod 755 filename 
	chmod 743 filename 
	chmod 043 filename 
	```
	  * -rwxr-xr-x
      * -rwxr---wx
      * ----r---wx
* `chown user filelist` - 
change owner of the file (value of user can be username or userid)
```text 
Note:- The super user, root has the unrestricted capability the ownership of any file but normal users can only change ownership of files they own.
```
* `chgrp group filelist` - 
change group of the file (value of group can be name of group or group id)
* `chmod ug+s dirname` - 
set SUID and SGID bit for a directory

## Pipes and Filters
* `|` - 
used when output of one command is to be taken as input for another program (pipe)

### Grep Command
* `grep pattern file(s)` - 
searches file or files for lines with a certain pattern  

  ```bash
  ls -l | grep "Com" 
  ```
    * search for files with "Com" and give the output in ls -l

```text
Note:- The order of execution in a pipe is from leftmost to rightmost
```
* Options with grep command:-
  * -v - print all lines that do not match pattern
  * -n - print all matched line and its line number
  * -l - print only the names of files with matching lines (letter "l")
  * -c - print only the count of matching lines 
  * -i - match either upper or lower case

    ```bash
    ls -l | grep -i "carol.*aug" 
    ```  
	* find lines with "carol", followed by 0 or more characters abbreviated as ".*", then followed by "aug"

### Sort Command
* `sort file` - 
sort the content of the file (alphabetically by default)
  ```text 
  Options with sort command:-
  -n - sort numerically (ex: 10 will sort after 2), ignore tabs and blanks
  -r - reverse the order of sort
  -f - sort lower and upper case together
  +x - ignore the first x fields when sorting
  ```

  ```bash
  ls -l | grep "Aug" | sort +4n 
  ```
    * sort all files in your directory modified in Aug by order of size (+4 skips 4 fields then sorts the lines in numeric order)
### pg and more Commands
If you run text through pg or more filters the display stops after each screenful of texts.
```bash
ls -l | grep "Auto" | sort +4n | more 
```
  * the screen will fill up with one screenful of text consisting of lines sorted by the order of file size. (at the bottom is the more prompt where you can type a command to move through the sorted text)

### find command
`find [path] [conditions] [actions]` - 
finds a file in given path according to conditions and perform given action.
* Path:
  * `find .` - start searching from the current directory to subdirectories
  * `find /` - start searching from the root directory (/bin, /etc, /var etc.)
* Options:
  * `-name` - file name (case sensitive)
  * `-iname` - file name (ignore case)
  * `-type f` - regular file
  * `-type d` - directory
  * `-type l` - symbolic links
  * `-size` - size of file 
    * `+` - for larger than
    * `-` - for less than
    * `G` - GiB (gibibytes = 1024 MiB = 1073741824)
    * `M` - MiB (mibibytes = 1024 KiB = 1048576)
    * `k` - KiB (kibibytes = 1024 bytes)
    * `c` - bytes
  * `-mtime n` - last modified (in n days) 
  * `-atime n` - last accessed (in n days)
  * `-ctime n` - metadata change time (in n days)
  ```text
  Note:- When find figures out how many 24-hour periods ago the file was last accessed, any fractional part is ignored. 
	 So  to  match -atime +1, a file has to have been accessed at least two days ago. 
  ```

  * `-user` - owned by user
  * `-group` - owned by group
  * `-perm` - file permissions
* Actions:
  * `-print` - print result (default)
  * `-delete` - delete file
  * `-exec command {} \;` - execute command on each result
