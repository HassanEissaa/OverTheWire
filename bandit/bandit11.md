---
layout: default
gamename: bandit
level: 11
---
Level Goal
----------
The password for the next level is stored in the file **data.txt**,
which contains base64 encoded data

Commands you may need to solve this level
-----------------------------------------
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

Helpful Reading Material
------------------------
- [Base64 on Wikipedia][]

[Base64 on Wikipedia]: http://en.wikipedia.org/wiki/Base64

Solution
--------------------------
```bash
bandit10@bandit:~$ man base64
bandit10@bandit:~$ base64 -d data.txt
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```
