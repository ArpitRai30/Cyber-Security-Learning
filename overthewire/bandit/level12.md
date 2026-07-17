# levle: 12
username: bandit12

## notes: 
* password is in a hexdump of a file which has been repeatedly compressed
* we can make a directory in /tmp in the server for working
* `mktemp -d` command can be used to make a directory with a random hard to guess name
* hexdump represents each byte(8 bits) in a two digit hexadecimal number 
* commands used are cp, mv, xxd, gzip, bzip2, tar

## approach:
* first copy the file in the working directory in /tmp
* try to reverse the hex dump using xxd command
* check type of file using `file` command for every file
* decompress the file repeatedly according to the enocde/zip type (use file command to know the type)
* you can use man command to know the decode command of different zip types 
* after multiple decompressions when you get the file type as ASCII then use cat to read the content

## solution:
```bash
mktemp -d
cd /tmp/tmp.generatedpath
xxd -r data.txt > data1
mv data1 data1.gz
gzip -d data1.gz
bzip2 -d data1
mv data1.out data1.gz
gzip -d data1.gz
tar -xf data1
tar -xf data5.bin
bzip2 -d data6.bin
tar -xf data6.bin.out
mv data8.bin data8.gz
cat data8
```
