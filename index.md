Hi!
hihi  
*I wonder if that line break up there worked >.>*  
## Matthew's To-Do List
- walk dog
- lunch
- tennis @3pm
> hungry... `monkey`

# Week 2 Lab Report

## Lab Instructions
Week 2 Lab Report
Before Friday, January 14, you’ll submit a lab report by writing a blog post like we just described. The topic will be remote access.

You will write a tutorial for incoming 15L students (and your future self!) about how to log into a course-specific account on ieng6. Your post should include the steps you took, along with screenshots of what each step looked like. You’re free to use the screenshots you took for lab 1, or new ones. Complete any steps you didn’t complete in your group on your own.

Overall, make sure you have at least 6 screenshots, one for each of the steps below (though more is useful, remember that this will help out your future self). For each step include 2-3 sentences or bullet points describing what you did.

## Step 1: Installing VScode
Download Visual Studio Code [here](https://code.visualstudio.com/download). Once you've completed the installation, the VS Code launch screen should look something like this:  

![Image](vscode-installed.png)
## Step 2: Remotely Connecting
The next step is to reset the password to activate your course-specific account. Once you know your newly set password, enter the following command in your terminal, but replacing the "aky" with the letters in your course-specific account.
> ssh cs15lwi22aky@ieng6.ucsd.edu

You will then be prompted with a yes/no quesitoning whether or not to allow the connection.
> ssh cs15lwi22aky@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 

Enter yes, then your password, and your connection will be initialized.

Once you've successfully established a connection, the output should look similar to the image below:

![image](remotely-connecting.png)  

## Step 3: Trying Some Commands
The next step is to start triyng out some command-line commands and observe the output. Some useful commands to know are `cd`, `ls`, `pwd`, and `scp`.

![image](trying-commands.png)  

## Step 4: Moving Files with scp
The `scp` (secure copy) command is useful for copying files and directories between two locations. The structure of this command is [`scp` + `file/directory` + `course-specific account` + `~/`]  The code block below illustrates how to copy a local file to your course-specfic account.
> scp HelloWord.java cs15lwi22aky@ieng6.ucsd.edu:~/

A screenshot of the line in terminal:

![image](scp-example.png)
## Step 5: Setting an SSH Key
SSH keys are a great way to avoid having to enter your password each time you want to copy over files to the server. To generate your key, enter `ssh-keygen`. The output should look something like:

![image](ssh-keygen.png)

Now you should no longer have to re-enter your password each time you want to ssh or scp.

## Step 6: Optimizing Remote Running
Finally, there are a few tips to help you navigate the command-line tools more efficiently. The first is to 
