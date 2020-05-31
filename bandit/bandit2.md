---
layout: default
gamename: bandit
level: 2
---
Level Goal
----------
The password for the next level is stored in a file called **-**
located in the home directory

Commands you may need to solve this level
-----------------------------------------
ls, cd, cat, file, du, find

Helpful Reading Material
------------------------
- [Google Search for "dashed filename"][]
- [Advanced Bash-scripting Guide - Chapter 3 - Special Characters][]

[Google Search for "dashed filename"]: https://www.google.com/search?q=dashed+filename
[Advanced Bash-scripting Guide - Chapter 3 - Special Characters]: http://tldp.org/LDP/abs/html/special-chars.html
Solution
--------------------------
```bash
$ ssh  bandit1@bandit.labs.overthewire.org -p 2220
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```
