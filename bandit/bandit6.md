---
layout: default
gamename: bandit
level: 6
---
Level Goal
----------
The password for the next level is stored in a file somewhere under
the **inhere** directory and has all of the following properties:
-   human-readable
-   1033 bytes in size
-   not executable

Commands you may need to solve this level
-----------------------------------------
ls, cd, cat, file, du, find

Solution
--------------------------
```bash
bandit5@bandit:~/inhere$ find . -size 1033c  ! -executable -type f
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```
