* `file filename` -
determine the type of a file
* Options with file:
  * `file ./*` -
  scan all files
  * `file -b` -
  remove filename from output
  * `file -z` -
  examines the content of a zipped file
  * `file -r` -
  don't recurse directories (if you give a directory file normally inspects files ins>

* `ls` -
list files
* Options with ls:
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
* `vi filename` -
vi editor, if file is present open it else create the file

* `touch filename` - 
if file exists edit its access and modification time to current time else create new >

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

* `strings filename` -
extracts all printable characters from any file
