# Week 2 Lab Report
This is the second lab report for CSE 15L that will material from lab 2 - servers and material from lab 3 - debugging.

## 1. Web server StringServer
This is my code for the web server called StringServer:
<img width="1064" alt="image" src="https://user-images.githubusercontent.com/122491071/215360637-5e350d83-0699-4eaa-8afa-7103f02d1aa6.png">

* There are two classes, Handler, which contains the class handleRequest that takes in a url of type URI as its parameter and returns a string. When the user first opens up the web server, meaning the path is only "/" and not anything else, it shows the message:  "Please enter a string: ." Once the user modifies the url and adds "/add-message?s=<string>" to the path, where <string> is the any string provided by the user, the whole path is split into two, the string portion before regex "=" and after it. The string portion after the "=," or parameters[1], is then concatenated to a once empty string called `inputs` and is conctatenated with a `"\n"` new line separator afterwards. Each time the user enters a new string, all the strings they have entered should accumulate, where the top is the oldest input, and the bottom is the newest input. The only values that should change is the string `inputs` after continuously adding more string to it, and the URI url parameter after the user has changed its path.

![image](https://user-images.githubusercontent.com/122491071/215361251-e384b9e5-2f90-480c-b301-88dced24c250.png)
![image](https://user-images.githubusercontent.com/122491071/215361268-0a8d043d-c22b-4651-a52c-dfc63934fcec.png)

* The two screenshots above show what happens when I use `add-message`. At first, the url of type URI changed since I added the path "add-message?s=slay". That would then change the string called `inputs` to "slay \n", where \n is a new line.

* The second time around, the url of type URI changed again since I added the path "add-message?s=yass". That would then change the string inputs to "slay \n yass \n", where "\n" is a new line.
  
2. **Web server StringServer**
3. **Something New I Learned**
Before lab 2, I did not know how to build and run a server on my local computer. It was interesting to learn how it worked and learn the terms `Ports` and `Localhost`
