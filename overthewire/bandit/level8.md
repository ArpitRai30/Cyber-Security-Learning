# level: 8
username: bandit8
password: `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`

## notes:
* search a file by line occurences to find the only line occuring once
* used sort and uniq commands with piping
* uniq -c gives line occurences of every line
* uniq -c counts only adjacent occurences that's why we have to sort the file before using it
* **solution:** `sort data.txt | uniq -c`

## things i didn't know before this level:
* counting occurences of a line
* using uniq command with piping


