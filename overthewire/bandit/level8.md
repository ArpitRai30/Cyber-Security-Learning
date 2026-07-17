# level: 8
username: bandit8

## notes:
* search a file by line occurences to find the only line occuring once
* used sort and uniq commands with piping
* uniq -c gives line occurences of every line
* uniq -c counts only adjacent occurences that's why we have to sort the file before using it
* uniq -u gives only unique occurences 
* **solution:** `sort data.txt | uniq -u`

## things i didn't know before this level:
* counting occurences of a line
* using uniq command with piping


