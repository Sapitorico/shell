# Shell, permissions
Multitasking and multiuser, meaning that more than one user can be operating the computer at the same time, to protect the users from each other, a series of permissions were created and managed by the following commands 
## comands

| commands           | description                                                               |
| ----------------- | ------------------------------------------------------------------ |
| **chmod** | modifies the rights of access to the archives |
| **su** | temporarily makes you a super user |
| **sudo** | temporarily makes you a super user, limited to only executing one command  |
| **chown** | change the file property  |
| **chgrp** | changes the ownership of the group |

Each file and directory is assigned access rights for the file owner, the related user group members and all others are assigned read, write and execute rights.
**ls -l shows permissions properties**

# As represented
![img](https://translate.google.com/website?sl=en&tl=es&hl=es&client=webapp&u=http://linuxcommand.org/images/file_permissions.png)
### chmod
specify the desired permission settings and the file to modify.

    rwx rwx rwx = 111 111 111
    rw-rw-rw- = 110 110 110
    rwx --- --- = 111 000 000
    
    y así...
    
    rwx = 111 en binario = 7
    rw- = 110 en binario = 6
    rx = 101 en binario = 5
    r-- = 100 en binario = 4### Features
# man or help:

* chmod
* sudo
* su
* chown
* chgrp
* id
* groups
* whoami
* adduser
* useradd
* addgroup
 
