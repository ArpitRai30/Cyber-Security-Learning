# Commands

## System Commands
whoami - username
passwd - reset password
users - name of all users
who - detail of users
logout - logout the user
halt - bring the system down immediately 
init 0 - power off the system using predefined scripts (switches system to runlevel 0)
init 6 - reboots the system (switches system to runlevel 6)
poweroff - shuts down the system immediately by powering off
shutdown - shuts down the system (can be scheduled and gives warning to logged in users
reboot - reboots the system (notifies users)

## File Commands 
ls - list files
ls -l - list files with more information
ls * - match 0 or more characters 
ls ? - match 1 character
ls -a - list files including hidden files
ls -lh - list files in human readable form (size in K,M,G)
ls -ld /example - list directories
ls -lt - list files based on last modified time (recent first)
ls -ltr - reverse order of lt (recent last)
ls -R - display files recursively
ls -F / ls --color=auto - display with colour (directories in blue, soft links in green, and ordinary files in default colour)
vi filename - vi editor, if file is present open it else create the file
touch filename - if file exists edit its access and modification time to current time else create new file
cat filename - display contents of a file
cat filename -b - display line numbers in file
wc filename1 filename1 - word count (totalLines totalWords totalSize(bytes) filename)
cp sourceFile destinationFile - copy file (if file is not in present directory then you need to provide complete path)
mv sourceFile destinationFile - move file
rm file1 file2 file3 - remove/delete file (use -i with rm to get a prompt before deletion)
 
## Directory Manangement
pwd - print working directory
mkdir /path - creates a new directory (creates inside working directory if path is not given)
mkdir -p /parent/dir - creates all necessary parent directories in between the path
rmdir dirname - removes the directory only if it is empty
cd - change directory
cd - - go to last directory 
mv olddir newdir - move/rename a directory 
