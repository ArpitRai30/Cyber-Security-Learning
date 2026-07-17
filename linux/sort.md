* `sort file` - 
sort the content of the file (alphabetically by default)
  ```text 
  Options with sort command:-
  -n - sort numerically (ex: 10 will sort after 2), ignore tabs and blanks
  -r - reverse the order of sort
  -f - sort lower and upper case together
  +x - ignore the first x fields when sorting
  -u - sort alphabetically and remove duplicate lines
  ```

  ```bash
  ls -l | grep "Aug" | sort +4n 
  ```
    * sort all files in your directory modified in Aug by order of size (+4 skips 4 fields then sorts the lines in numeric order)
