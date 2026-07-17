# level: 9
username: bandit9
password: `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

## notes:
* had to search for human readable strings in a data file, preceded by several '='
* used strings command which extracts all printable characters from any file
* used pipeline to filter through the strings by '='
* **solution:** `strings data.txt | grep '='`

## things i didn't know before this level:
* string command 
* using grep on data file doesn't produce desired output, you either have to use -a for grep to treat the file as text or change input through pipeline

