---
layout: default
gamename: bandit
level: 7
---
Level Goal
----------
The password for the next level is stored **somewhere on the
server** and has all of the following properties:
-   owned by user bandit7
-   owned by group bandit6
-   33 bytes in size

Commands you may need to solve this level
-----------------------------------------
ls, cd, cat, file, du, find, grep

Solution
--------------------------
```bash
bandit6@bandit:~$ find / size- 33c -user bandit7 -group bandit6 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```
Explanation
--------------------------
find / : starts at the root
2>: file redirects stderr to file dump it to /dev/null
