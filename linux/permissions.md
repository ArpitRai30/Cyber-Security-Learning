(group of rwx - read, write, execute)
(3 types - owner/user(u), group(g), other(o))
* `chmod` - change permissions (symbolic and absolute methods)
  * **Symbolic:**

    ```bash
    chmod o+wx filename 
    chmod u-x filename 
    chmod g=rx filename 
    ```

    * add write and exe permission to other
    * remove exe permission from owner/user
    * give only read and exe permission to group

  * **Absolute:**

    ```text
    0 : ---
        1 : --x
        2 : -w-
        3 : -wx
        4 : r--
        5 : r-x
        6 : rw-
        7 : rwx
        ```

        ```bash
        chmod 755 filename 
        chmod 743 filename 
        chmod 043 filename 
        ```
          * -rwxr-xr-x
      * -rwxr---wx
      * ----r---wx
* `chown user filelist` -
change owner of the file (value of user can be username or userid)
```text 
Note:- The super user, root has the unrestricted capability the ownership of any file>
```
* `chgrp group filelist` -
change group of the file (value of group can be name of group or group id)
* `chmod ug+s dirname` -
set SUID and SGID bit for a directory
