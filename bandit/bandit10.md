---
layout: default
gamename: bandit
level: 10
---
Level Goal
----------
The password for the next level is stored in the file **data.txt**
in one of the few human-readable strings, preceded by several '='
characters.

Commands you may need to solve this level
-----------------------------------------
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

Solution
--------------------------
```bash
bandit9@bandit:~$ strings data.txt | grep ====
========== the*2i4
========== password
Z)========== is
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```
