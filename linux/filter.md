* `|` -
used when output of one command is to be taken as input for another program (pipe)

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
        * find lines with "carol", followed by 0 or more characters abbreviated as ".*", then followed by "aug"```

* If you run text through pg or more filters the display stops after each screenful of texts.
```bash
ls -l | grep "Auto" | sort +4n | more 
```
  * the screen will fill up with one screenful of text consisting of lines sorted by the order of file size. (at the bottom is the more prompt where you can type a command to move through the sorted text)

* `uniq filename` -
removes adjacent duplicate lines
* Options with uniq command:-
  * -c - count occurences
  * -d - show only duplicate lines
  * -u - show only unique (non-repeated) lines
  * -i - ignore case (lowercase = uppercase)
