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
3. Once you have found your username, click the link on-screen [Global Password Change Tool](https://sdacs.ucsd.edu/~icc/password.php) to reset your password for this account. Wait a couple minutes after resetting your password before continuing to the next step.
4. *I skipped this step because I am using a Mac*.                                                                                                        If you are on Windows, install Git for Windows at this [link](https://gitforwindows.org/). Once you have Git installed, follow the instructions at this [link](https://stackoverflow.com/questions/42606837/how-do-i-use-bash-on-windows-from-the-visual-studio-code-integrated-terminal/50527994#50527994) in order to use Bash in VScode. If you are not on Windows, skip this step and continue to the next.
5. Open up a terminal in VScode. Enter the following command into the terminal:
```
$ ssh cs15lsp23zz@ieng6.ucsd.edu
```
Replace the "zz" with the two letters in your course-specific account. For example, my account is cs15lsp23aw, so I would enter `$ ssh cs15lsp23aw@ieng6.ucsd.edu`  into the terminal. 
6. Enter your newly-created password when prompted. The terminal should look something like this once finished. ![Image](Screen Shot 2023-04-07 at 6.51.24 PM.png). 


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

