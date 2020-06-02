---
layout: default
gamename: bandit
level: 13
---
Level Goal
----------
The password for the next level is stored in the file **data.txt**,
which is a hexdump of a file that has been repeatedly compressed.
For this level it may be useful to create a directory under /tmp in
which you can work using mkdir. For example: mkdir /tmp/myname123.
Then copy the datafile using cp, and rename it using mv (read the
manpages!)

Commands you may need to solve this level
-----------------------------------------
grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir,
cp, mv, file

Helpful Reading Material
------------------------
- [Hex dump on Wikipedia][]

[Hex dump on Wikipedia]: http://en.wikipedia.org/wiki/Hex_dump
```bash
bandit12@bandit:~$ mkdir /tmp/level12
bandit12@bandit:~$ cp data.txt /tmp/level12
bandit12@bandit:~$
bandit12@bandit:~$ cd /tmp/level12
bandit12@bandit:/tmp/level12$ ls
data.txt
bandit12@bandit:/tmp/level12$ xxd -r data.txt rhex
bandit12@bandit:/tmp/level12$ file rhex
bandit12@bandit:/tmp/level12$ mv rhex rhex.gz
bandit12@bandit:/tmp/level12$ gzip -d rhex.gz
bandit12@bandit:/tmp/level12$ file rhex
rhex: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/level12$ bzip2 -d rhex
bzip2: Cant guess original name for rhex -- using rhex.out
bandit12@bandit:/tmp/level12$ file rhex.out
rhex.out: gzip compressed data, was "data4.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/level12$ mv rhex.out rhex.gz
bandit12@bandit:/tmp/level12$ gzip -d rhex.gz rhex
gzip: rhex: unknown suffix -- ignored
bandit12@bandit:/tmp/level12$ tar -xvf rhex
data5.bin
bandit12@bandit:/tmp/level12$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/level12$ tar -xvf data5.bin
data6.bin
bandit12@bandit:/tmp/level12$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/level12$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/level12$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/level12$ ls
data5.bin  data6  data.txt  rhex  unhex  unhex2
bandit12@bandit:/tmp/level12$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/level12$ tar -xvf data6
data8.bin
bandit12@bandit:/tmp/level12$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix
bandit12@bandit:/tmp/level12$ mv data8.bin data8.gz
bandit12@bandit:/tmp/level12$ gzip -d data8.gz
bandit12@bandit:/tmp/level12$ ls
data5.bin  data6  data8  data.txt  rhex  unhex  unhex2
bandit12@bandit:/tmp/level12$ file data8
data8: ASCII text
bandit12@bandit:/tmp/level12$ cat data8
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```
