# level: 5
username: bandit5
password: `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`

## notes: 
* had to search for a file with given criteria
* used find with -readable, -size, and -perm options to filter with readable, size 1033c(bytes) and permission -u-x(not executable) option 
* **solution:**
  ```bash
  cd inhere
  find -readable -size 1033c -perm -u-x
  cat ./maybehere07/.file2
  ```

## things i didn't know before this level:
using different options with find command
