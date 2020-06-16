# Find Command:-

## Overview

Find command is used to find the files or directory’s path, it is exactly like the find option in windows where you can search for a file. 
 
Syntax: `find / (under root) –option filename `
 
Options that can be used with find command: 
 
 | Option | Usage|
 | :---:| :--|
 | -name | For searching a file with its name |
 | -inum | For searching a file with particular inode number |
 | -type | For searching a particular type of file |
 | -user | For files whose owner is a particular user |
 | -group| For files belonging to particular group |
 
## Working with find command

* Finding a File with name   
$ `find -name samplefile`

```
./krishna/samplefile
``` 

* Finding a file with its inode number     
$ `find / -inum 8444249301491656`   
Note: Use `ls -il` command to find inode value   
```
$ ls -il
total 0
10133099161755539 drwxrwxrwx 1 root krishnaprasadkv 4096 May 27 14:45 sampledir
 8444249301491656 -rwxrwxrwx 1 root krishnaprasadkv    0 May 27 14:45 samplefile
$ find -inum 8444249301491656
./krishna/samplefile
```
* Finding the files, whose owner is a user called krishnaprasadkv   
$ `find / -user krishnaprasadkv`   
```
/home/krishnaprasadkv/Technology  
/home/krishnaprasadkv/Technology/Cloud  
/home/krishnaprasadkv/Technology/Cloud/AWS  
/home/krishnaprasadkv/Technology/Cloud/Azure  
/home/krishnaprasadkv/Technology/Cloud/GCP  
/home/krishnaprasadkv/Technology/Devops  
/home/krishnaprasadkv/Technology/Devops/ansible  
/home/krishnaprasadkv/Technology/Devops/docker  
/home/krishnaprasadkv/Technology/Devops/kubernetes  
/home/krishnaprasadkv/Technology/test  
/home/krishnaprasadkv/–P  
/home/krishnaprasadkv/test.c  
/home/krishnaprasadkv/testing  
/home/krishnaprasadkv/testing/test.json  
```  
* Finding the files whose group is “ktgroup”   
$ `find / -group ktgroup`   
  ```
/home/krishnaprasadkv/Technology  
/home/krishnaprasadkv/Technology/Cloud  
/home/krishnaprasadkv/Technology/Cloud/AWS  
/home/krishnaprasadkv/Technology/Cloud/Azure  
/home/krishnaprasadkv/Technology/Cloud/GCP  
/home/krishnaprasadkv/Technology/Devops  
/home/krishnaprasadkv/Technology/Devops/ansible  
/home/krishnaprasadkv/Technology/Devops/docker  
/home/krishnaprasadkv/Technology/Devops/kubernetes  
/home/krishnaprasadkv/Technology/test  
/home/krishnaprasadkv/–P  
/home/krishnaprasadkv/test.c  
/home/krishnaprasadkv/testing  
/home/krishnaprasadkv/testing/test.json  
 ```

* Finding the files have not been accessed
$ `find ./Technology/  -atime +2`
```
/home/krishnaprasadkv/Technology/
/home/krishnaprasadkv/Technology/Cloud
/home/krishnaprasadkv/Technology/Cloud/AWS
/home/krishnaprasadkv/Technology/Cloud/Azure
/home/krishnaprasadkv/Technology/Cloud/GCP
/home/krishnaprasadkv/Technology/Devops
/home/krishnaprasadkv/Technology/Devops/ansible
/home/krishnaprasadkv/Technology/Devops/docker
/home/krishnaprasadkv/Technology/Devops/kubernetes
```

* Finding the file have not been modified 
$ `find ./Technology/  -mtime +2`
```
/home/krishnaprasadkv/Technology/Cloud
/home/krishnaprasadkv/Technology/Cloud/AWS
/home/krishnaprasadkv/Technology/Cloud/Azure
/home/krishnaprasadkv/Technology/Cloud/GCP
/home/krishnaprasadkv/Technology/Devops/docker
/home/krishnaprasadkv/Technology/Devops/kubernetes
```

* List help page of find command with their option.   
$ `find --help`
```
find --help
Usage: find [-H] [-L] [-P] [-Olevel] [-D help|tree|search|stat|rates|opt|exec|time] [path...] [expression]

default path is the current directory; default expression is -print
expression may consist of: operators, options, tests, and actions:

operators (decreasing precedence; -and is implicit where no others are given):
      ( EXPR )   ! EXPR   -not EXPR   EXPR1 -a EXPR2   EXPR1 -and EXPR2
      EXPR1 -o EXPR2   EXPR1 -or EXPR2   EXPR1 , EXPR2

positional options (always true): -daystart -follow -regextype

normal options (always true, specified before other expressions):
      -depth --help -maxdepth LEVELS -mindepth LEVELS -mount -noleaf
      --version -xdev -ignore_readdir_race -noignore_readdir_race

tests (N can be +N or -N or N): -amin N -anewer FILE -atime N -cmin N
      -cnewer FILE -ctime N -empty -false -fstype TYPE -gid N -group NAME
      -ilname PATTERN -iname PATTERN -inum N -iwholename PATTERN -iregex PATTERN
      -links N -lname PATTERN -mmin N -mtime N -name PATTERN -newer FILE
      -nouser -nogroup -path PATTERN -perm [-/]MODE -regex PATTERN
      -readable -writable -executable
      -wholename PATTERN -size N[bcwkMG] -true -type [bcdpflsD] -uid N
      -used N -user NAME -xtype [bcdpfls]
      -context CONTEXT


actions: -delete -print0 -printf FORMAT -fprintf FILE FORMAT -print
      -fprint0 FILE -fprint FILE -ls -fls FILE -prune -quit
      -exec COMMAND ; -exec COMMAND {} + -ok COMMAND ;
      -execdir COMMAND ; -execdir COMMAND {} + -okdir COMMAND ;
```

