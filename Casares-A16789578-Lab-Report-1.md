# Week 1 Lab Report
This is the first lab report for CSE 15L that will cover the first lab conducted today, 1/11/23, which involves installing VScode, remotely connecting, and trying certain commands.

1. **Installing VScode**
* My laptop already had VScode downloaded prior because of my CSE 11 class last quarter. If you do not already have it downloaded, you can go to https://code.visualstudio.com/ and follow the directions to download the application. 
* Below is a screenshot of what the application looks like:
<img width="1440" alt="Screen Shot 2023-01-11 at 1 16 57 PM" src="https://user-images.githubusercontent.com/122491071/211950930-0a28bcf0-f444-4273-8d9a-2aad40a8eea0.png">

2. **Remotely Connecting**
* These are the directions to follow for Mac devices, which is what I used. Open VScode, then click 'Terminal' at the top bar, and open a new terminal.
* Use ssh by typing ssh cs15lwi23zz@ieng6.ucsd.edu, where you put your course-specific account instead of the placeholder 'zz'.
* When asked to continue connecting, type 'yes' and enter the password of your CSE15L account, then click enter to connect. The characters of your password may not appear as you are typing, but do not fret since this is likely for security purposes. Do not forget to disconnect (Ctrl-D or Command-D) once you are done.
<img width="1106" alt="Screen Shot 2023-01-11 at 5 07 41 PM" src="https://user-images.githubusercontent.com/122491071/211951728-8b3b6668-b5de-42d0-b094-a07aad8973e6.png">

3. **Trying Some Commands*
* After completing step 2, try some commands such as :
```
cd ~
cd
ls -lat
```
* For example, running the command ls -lat seems to list out the files of the directory I am currently working in. This is what it should look similar to:
<img width="1195" alt="Screen Shot 2023-01-11 at 5 14 01 PM" src="https://user-images.githubusercontent.com/122491071/211952387-95337b17-92b3-4faf-b622-03fa42faadaf.png">

