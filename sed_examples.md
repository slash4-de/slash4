Replace newlines with sed
==========================

Sed is a powerful tool to manipulate strings or streams (sed = Stream EDitor). 
A comparison of using sed to replace newlines with other tools can be found here: 
https://slash4.de/blog/python/sed-replace-newline-or-python-awk-tr-perl-xargs.html

The sed syntax is basically: 

```
sed 's/SEARCH/REPLACE/g'
```

And to replace newlines you would use:

```
sed ':a;N;$!ba;s/\n/ /g'
```

For example:


```
user@slash4.de:~$ cat example.txt | sed ':a;N;$!ba;s/\n/ /g'
line 1 line 2 line 3 line 4 line 5
```
