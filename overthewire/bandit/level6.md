# level: 6
username: bandit6
password: `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`

## notes:
* had to perform a search in root directory for the file with given owner, group, and size
* use find / to search in the root directory 
* use -user, -group, -size with find to filter by owner, group, and size
* use 2>/dev/null with find to redirect stderr(2) to /dev/null(a location which accepts everything but saves nothing).
* every process has 3 channels: 
  * 0: stdin (input)
  * 1: stdout (normal output)
  * 2: stderr (error messages)
* **solution:** 
  ```bash
  find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
  cat /var/lib/dpkg/info/bandit7.password
  ```

## things i didn't know before this level:
* difference between find . and find /
* how to redirect error messages to /dev/null
