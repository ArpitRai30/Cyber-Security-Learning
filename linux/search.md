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
    * `G` - GiB (gibibytes = 1024 MiB = 1073741824 bytes)
    * `M` - MiB (mibibytes = 1024 KiB = 1048576 bytes)
    * `k` - KiB (kibibytes = 1024 bytes)
    * `c` - bytes
  * `-mtime n` - last modified (in n days)
  * `-atime n` - last accessed (in n days)
  * `-ctime n` - metadata change time (in n days)

    ```text
    Note:- When find figures out how many 24-hour periods ago the file was last accessed, any fractional part is ignored. So  to  match -atime +1, a file has to have been accessed at least two days ago. 
    ```

  * `-user` - owned by user
  * `-group` - owned by group
  * `-perm` - file permissions
* Actions:
  * `-print` - print result (default)
  * `-delete` - delete file
  * `-exec command {} \;` - execute command on each result
