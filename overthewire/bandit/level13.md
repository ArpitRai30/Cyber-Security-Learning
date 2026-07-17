# level: 13
username: bandit13
password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

## notes:
* ssh login using keys works as: ssh creates 2 keys private and public. The private keys resides at your local machine in /.ssh/keyname and the public key /.ssh/keyname.pub
* The private key never leaves your machine (not even during verification). 
* You login to the server you want to connect ssh key to and add your public key to its /.ssh/authorized_keys directory. 
* After adding the public key to authorized key the server will check for its pair whenever you login and the private key present on your machine will give you access to login.
* Set permission for .ssh as 700 and keyname as 600 for security.
* `ssh-keygen -t rsa` command is used to generate the pair of keys.
* `ssh-copy-id <username>@<host>` command can be used to add the public key to the server using password once.

## approach:
* you get the private key for the next level in this level.
* try to replicate the conditions as if the key was generated on your machine.
* recheck and edit file permissions to match the security requirements.
