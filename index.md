# Lab Report 3

There are multiple different ways to use the `find` command to search for files or directories based on certain criteria. Below are a few useful ways to use this command. 

## Find and list every directory within a given directory

`$ find [directory] -type d` 
This command will list every directory within a given directory. This command is useful if you want to search only for directories within a directory hierarchy. Below are some examples. 
```
$ find technical/government -type d
technical/government
technical/government/About_LSC
technical/government/Env_Prot_Agen
technical/government/Alcohol_Problems
technical/government/Gen_Account_Office
technical/government/Post_Rate_Comm
technical/government/Media
```
The command shown above is searching through and listing each directory in `technical/government`. 
```
$ find technical -type d
technical
technical/government
technical/government/About_LSC
technical/government/Env_Prot_Agen
technical/government/Alcohol_Problems
technical/government/Gen_Account_Office
technical/government/Post_Rate_Comm
technical/government/Media
technical/plos
technical/biomed
technical/911report
```
The command shown above is searching through and listing each directory in `technical`.

## Find and delete files
`$ find -name [name] -delete`
This command will find and delete each file within a directory that matches the given name. This command is useful if you want to delete all files within a directory that match a certain criteria by doing just one command. Below are some examples.
```
$ find technical -name "chapter-1.txt" -delete
```
The command shown above produces no output, but it deleted the file with the name "chapter-1.txt" under "technical". 
```
$ find technical/government/Env_Prot_Agen "*.txt" -delete
```
The command shown above produces no output, but it deleted all files ending in ".txt" in "technical/government/Env_Prot_Agen". 

## Find files greater than some size
`$ find [directory] -size [number][unit]`
This command will find and list all files within a directory by file size. This is particularly useful because you can specify a size and units (bytes, kilobytes, megabytes, etc) and you can use "+" or "-" to list files greater than or less than a certain specified size. 
```
$ find technical/plos -size +29k
technical/plos/pmed.0020059.txt
technical/plos/pmed.0020073.txt
technical/plos/pmed.0020249.txt
technical/plos/pmed.0020103.txt
technical/plos/pmed.0010028.txt
technical/plos/pmed.0010064.txt
technical/plos/pmed.0020018.txt
technical/plos/pmed.0020182.txt
technical/plos/pmed.0020246.txt
technical/plos/pmed.0020045.txt
technical/plos/pmed.0010036.txt
```
The command shown above is searching through technical/plos and listing all files greater than 29 kilobytes in that directory. The "+" is used in front of 29 to find files greater than the specified size (29), and the "k" is used after 29 to specify the unit of kilobytes. 
```
$ find technical/911report -size -10000c
technical/911report
technical/911report/preface.txt
```
The command shown above is searching through technical/911report and listing all files less than 10000 bytes in that directory. The "-" is used in front of 10000 to find files less than the specified size (10000), and the "c" is used after 10000 to specify the unit of bytes. 

## Find files based on time last modified
`$ find technical -mtime [days]`
This command will search through a given directory and list all files and directories modified within a given time frame. This is useful because you can search for both files and directories that have been modified a specific number of days ago, within a certain number of days, or greater than a certain number of days ago. This can be done by adding "+" or "-".
```
$ find technical -mtime -7
technical
technical/government
technical/.DS_Store
technical/plos/journal.pbio.0020010.txt
technical/911report
technical/911report/chapter-11.txt
```
The command shown above is searching through technical and listing all files and directories that have been modified within the past 7 days. The "-" in front of 7 is used to find files and directories that have been modified within the past specified number of days.
```
$ find technical/plos -mtime +30
```
The command shown above is searching through technical/plos to find files and directories that have been modified greater than 30 days ago. The "+" in front of 30 is used to find files and directories that have been modified greater than the specified number of days. No output was produced, meaning that there are no files or directories in technical/plos that have been modified greater than 30 days ago. 


*For each of the command shown above, I used ChatGPT*
