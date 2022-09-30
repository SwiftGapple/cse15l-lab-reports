# Lab1 Report


## 1. Installing VScode
![Image](lab1img/img1.PNG)
* Download VSCode at the website(trivial)

## 2. Remotely Connecting
![Image](lab1img/img2.PNG)
* First change ucsd tritonlink password
(force the system to update the password for this class)
* use the terminal in VSCode to use SSH to connect
* $ SSH cs15lfa22(xx)@ieng6.ucsd.edu
* wait for prompt and input the password
* by default you can't see your password while typing

## 3. Trying Some Commands
![Image](lab1img/img3.PNG)
* $ pwd: print working directory
* $ ls: list the files in the current directory
* $ cd: change directory
* $ cp: copy file

## 4. Moving Files with scp
![Image](lab1img/img4.PNG)
* use command $ scp "file name" cs15lfa22(xx)@ieng6.ucsd.edu:~/ to upload the file
* enters the password
* should be visible in the remote server

## 5. Setting an SSH Key
![Image](lab1img/img5.PNG)
* use command $ ssh-keygen to initialize ssh key generator
* type in the directory on your computer where you want to
store the ssh keys
* no need for passphrase so just type noting in the following prompts

## 6. Optimizing Remote Running
![Image](lab1img/img6.PNG)
* $ ssh cs15lfa22(xx)@ieng6.ucsd.edu "ls" for direct access to list the files
* use the up arrow to retrieve previous command to save some time
* now with the ssh file we can enter the server without typing the password
