---
layout: default
gamename: bandit
level: 4
---
Level Goal
----------
The password for the next level is stored in a hidden file in the
**inhere** directory.

Commands you may need to solve this level
-----------------------------------------
ls, cd, cat, file, du, find

Solution
--------------------------
```bash
bandit3@bandit:~$ ls -a
.  ..  .bash_logout  .bashrc  inhere  .profile
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```
