# Lab Report 1
## Step 1 - Installing VScode
*Because I already had VScode installed from a previous course, I skipped this step. This is what VScode should look like once downloaded.*
If you do not already have VScode installed, click this [link](https://code.visualstudio.com/) to download it. 
This is what the website should look like. Click the download link that corresponds to the operating system that you have. 

![Image](Screen Shot 2023-04-07 at 8.59.28 PM.png)

Once VScode has been successfully installed, this is what it should (in general) look like.

![Image](Screen Shot 2023-04-06 at 11.24.02 AM.png)


## Step 2 - Remotely Connecting
1. First, you need to look up your course-specific CSE 15L account. Click this [link](https://sdacs.ucsd.edu/~icc/index.php) and log-in using your username and PID.
2. Once logged in, find your CSE15L account username. It should start with "cs15lsp23" followed by 2 unique characters. ![Image](Screen Shot 2023-04-07 at 9.19.51 AM.png)
3. Once you have found your username, click the link on-screen [Global Password Change Tool](https://sdacs.ucsd.edu/~icc/password.php) to reset your password for this account. Wait a couple minutes after resetting your password before continuing to the next step. ![Image](Screen Shot 2023-04-08 at 10.13.54 PM.png)
4. *I skipped this step because I am using a Mac*.                                                                                                        If you are on Windows, install Git for Windows at this [link](https://gitforwindows.org/). Once you have Git installed, follow the instructions at this [link](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994) in order to use Bash in VScode. If you are not on Windows, skip this step and continue to the next.
5. Open up a terminal in VScode. Enter the following command into the terminal:
```
$ ssh cs15lsp23zz@ieng6.ucsd.edu
```
Replace the "zz" with the two letters in your course-specific account. For example, my account is cs15lsp23aw, so I would enter `$ ssh cs15lsp23aw@ieng6.ucsd.edu`  into the terminal. 
6. Enter your newly-created password when prompted. The terminal should look something like this once finished. 

![Image](Screen Shot 2023-04-07 at 6.51.24 PM.png). 


## Step 3 - Trying Some Commands
After connecting remotely, the next step is to try some commands. I entered the following commands into the terminal:
- `pwd`
- `ls`
- `ls -lat`
- `cat /home/linux/ieng6/cs15lsp23/public/hello.txt`
- `cd`
- `ls -a`
- `mkdir`
- `cp`

This is what my terminal looked like after entering each of those commands:
![Image](Screen Shot 2023-04-07 at 7.28.47 PM.png)


# Lab Report 2
##Part 1
![Image](Screen Shot 2023-05-06 at 4.05.56 PM.png)
![Image](Screen Shot 2023-05-06 at 4.07.20 PM.png)
![Image](Screen Shot 2023-05-06 at 4.07.36 PM.png)

















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
