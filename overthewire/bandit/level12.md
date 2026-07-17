# levle: 12
username: bandit12
password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

## notes: 
* password is in a hexdump of a file which has been repeatedly compressed
* we can make a directory in /tmp in the server for working
* `mktemp -d` command can be used to make a directory with a random hard to guess name
* hexdump represents each byte(8 bits) in a two digit hexadecimal number 
* commands used are cp, mv, xxd, gzip, bzip2, tar

## approach:
* first copy the file in the working directory in /tmp
* try to reverse the hex dump using xxd command
* decompress the file repeatedly according to the zip type (use file command to know the type)
* you can use man command to know the decode command of different zip types 
* after multiple decompressions when you get the file type as ASCII then use cat to read the content
