# Week 1 Lab Report
This is the first lab report for CSE 15L that will cover the first lab conducted today, 1/11/23, which involves installing VScode, remotely connecting, and trying certain commands.

1. **Installing VScode**
* My laptop already had VScode downloaded prior because of my CSE 11 class last quarter. If you do not already have it downloaded, you can go to [Link] (https://code.visualstudio.com/) and follow the directions to download the application. 
* Below is a screenshot of what the application looks like:
<img width="1440" alt="Screen Shot 2023-01-11 at 1 16 57 PM" src="https://user-images.githubusercontent.com/122491071/211950930-0a28bcf0-f444-4273-8d9a-2aad40a8eea0.png">

2. **Remotely Connecting**
* These are the directions to follow for Mac devices, which is what I used. Open VScode, then click `Terminal` at the top bar, and open a new terminal.
* Use ssh by typing `ssh cs15lwi23zz@ieng6.ucsd.edu`, where you put your course-specific account instead of the placeholder 'zz'.
* When asked to continue connecting, type `yes` and enter the password of your CSE15L account, then click enter or return to connect. The characters of your password may not appear as you are typing, but do not fret since this is likely for security purposes. Do not forget to disconnect (`Ctrl-D` or `Command-D`) once you are done.
* Below is a screenshot of what it should look like once you have connected. It should include your last login date, and a notice specifying that this system is only for use of the holder of the account:
<img width="1214" alt="image" src="https://user-images.githubusercontent.com/122491071/215237438-76764a5d-1e7f-4354-8af9-ca18f26489a7.png">

3. **Trying Some Commands**
* After completing step 2, try some commands such as :
```
cd 
ls
ls -lat
cd ~
pwd
```

* For example, say we were to run the command `ls`, it should list all your directories. This is what directories I have two directories: `perl5` and `wavelet`:
<img width="952" alt="image" src="https://user-images.githubusercontent.com/122491071/215311600-316f5deb-4c0d-49a1-849b-f49b128d54ec.png">

* Continuing off the previous example, the command `cd`, which stands for 'change directories', afterwards would take us to the specified directory. If I want to go to the directory called `wavelet`, I would enter the command `cd wavelet`. I can then use the `ls` command to list the files I have in that directory. The screenshot below shows the previous `cd` command and that my wavelet folder holds 8 files after the second `ls` command:
<img width="952" alt="image" src="https://user-images.githubusercontent.com/122491071/215238017-d3ea435c-b86b-46cb-93ca-e96fa3e38a1e.png">

* A different example is running the command `ls -lat` seems to list out the files of the directory I am currently working in. This is what it should look similar to :
<img width="1195" alt="Screen Shot 2023-01-11 at 5 14 01 PM" src="https://user-images.githubusercontent.com/122491071/211952387-95337b17-92b3-4faf-b622-03fa42faadaf.png">

* This is a longer example in which I continue off the second example. After changing my directory to `wavelet` with the `cd` command and after I use `ls` to list all the files in the directory, I run the command `cd ~` to take me back to the home directory. The command `pwd`('print working directory') confirms that I have been taken back to the home directory. This is what it should look like:

<img width="952" alt="image" src="https://user-images.githubusercontent.com/122491071/215311416-848cbb2e-d54b-4c24-be3c-d70c645518fe.png">


