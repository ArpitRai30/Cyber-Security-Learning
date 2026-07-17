## base64 encoding
* Base64 is a binary-to-text encoding that uses 64 printable characters to represent Base64 is a binary-to-text encoding that uses 64 printable characters to represent binary data as ASCII text.
* `base64 filename` -
encodes the contents of a file in base64
* `base64 -d filename` -
decodes the content of a base64 encoded file

## rot13 cypher
* ROT13 is a simple letter substitution cipher that replaces a letter with the 13th letter after it in the alphabet
* using rot13 again on the cypher decodes it since 13x2=26.
* `echo 'text' | tr 'A-Za-z' 'N-ZA-Mn-za-m'` -
it uses tr command to implement rot13 cypher on text
* `tr` -
it means translate, it replaces every occurence of a character from the first set with the corresponding character from the second set. It is commonly used to translate, delete, or squeeze repeated characters from standard input.
  * ex:- ```echo 'abc' | tr 'abc' 'xyz'```

## hex dump
* In a hex dump, each byte (8 bits) is represented as a two-digit hexadecimal number.
* `xxd file > hex-file` -
converts the file in hexdump in new file
* `xxd -r file > rev-file` -
reverse the hex dump in new file
