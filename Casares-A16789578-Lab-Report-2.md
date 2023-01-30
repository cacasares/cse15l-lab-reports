# Week 2 Lab Report
This is the second lab report for CSE 15L that will material from lab 2 - servers and material from lab 3 - debugging.

## 1. Web server StringServer
---
This is my code for the web server called StringServer:
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String inputs="";

    public String handleRequest(URI url) {
        //this message to enter a string should return once the user first opens the webpage
        if (url.getPath().equals("/")) {
            //intial message
            return String.format("Please enter a string: ");
            //if the user includes a path that has '/add-message', take the string after the '='
        } else if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            //continuously concatenate the string (/add-message?s=<string>) after the '=' to the initialized empty string input
            inputs+= parameters[1]+ "\n";
            return String.format(inputs);
        } else {
            System.out.println("Path: " + url.getPath());
            return "404 Not Found!";
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
* There are two classes, `Handler`, which contains the class `handleRequest` that takes in a `url` of type `URI` as its `parameter` and `returns` a `string`. When the user first opens up the web server, meaning the path is only "/" and not anything else, it shows the message:  "Please enter a string: ." Once the user modifies the url and adds "/add-message?s=<string>" to the path, where `<string>` is the any string provided by the user, the whole path is split into two, the string portion before regex "=" and after it. The string portion after the "=," or parameters[1], is then concatenated to a once empty string called `inputs` and is conctatenated with a `"\n"` new line separator afterwards. Each time the user enters a new string, all the strings they have entered should accumulate, where the top is the oldest input, and the bottom is the newest input. The only values that should change is the string `inputs` after continuously adding more string to it, and the URI url parameter after the user has changed its path.

![image](https://user-images.githubusercontent.com/122491071/215361251-e384b9e5-2f90-480c-b301-88dced24c250.png)
![image](https://user-images.githubusercontent.com/122491071/215361268-0a8d043d-c22b-4651-a52c-dfc63934fcec.png)

* The two screenshots above show what happens when I use `add-message`. At first, the url of type URI changed since I added the path "add-message?s=slay". That would then change the string called `inputs` to "slay \n", where \n is a new line.

* The second time around, the url of type URI changed again since I added the path "add-message?s=yass". That would then change the string inputs to "slay \n yass \n", where "\n" is a new line.
  
## 2. Debugging
---
## Reversed Method - Original Code

```
  public class ArrayExamples {

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
  }
```
                                  
## Test- Failure Inducing Input
                                  
```  
  @Test
  public void testReversed2() {
    int[] input2 = {1,2,3};
    int [] output= ArrayExamples.reversed(input2);
    assertArrayEquals(new int[]{3,2,1}, output);
  }
  ```
                                  
> I tested the reversed method with the input of {1,2,3} and I expected the output of `3` as the first element of the array, but instead got `0`.
  
## Test- Non-Failure Inducing Input
```
  @Test
  public void testReversed2() {
    int[] input2 = {0};
    int [] output= ArrayExamples.reversed(input2);
    assertArrayEquals(new int[]{0}, output);
  }
```
    
> I tested the reversed method with the input of {0} and I expected the output of `0` as the first element of the array, and got `0`. I will explain why this input passed during the last step.
## Symptom 
<img width="1440" alt="image" src="https://user-images.githubusercontent.com/122491071/215366017-35d80edf-1e85-40ed-9011-f5cbf7ebc116.png">
    
> The behavior shown in the screenshot above shows that two tests ran, but one failed. The first test had a failure-inducing input, the array {1,2,3}. The symptom was that it returned `0` when I expected the first element of the reversed list to be `3`. For the second test, the input was the array {0} and the symptom was it returned 0 as the element in the array because the although the array assignment in the original code was incorrect, the default values of initialized arrays are 0s for ints, hence why the test passed. I will expand more on the bug below. 

## Fixed Reversed Method
```
    static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      //arr[i] = newArray[arr.length - i - 1];
      newArray[i]=arr[arr.length - i - 1];
    }
    arr=newArray;
    return arr;
  }
```
                                  
> This revised version works now because the reversed values of the array are now correctly being placed into the newArray. Before hand, the assignment was `arr[i] = newArray[arr.length - i - 1];`, which was giving values from newArray, which has default values of 0, to arr. That is why the value that is actually there are only 0s and why the second test passed. To fix the problem, we can simply assign the values of newArray correctly, where the elements at the last index until the 0th index of arr are given to newArray with the proper assignment order `newArray[i]=arr[arr.length - i - 1];`.

---

## 3. Something New I Learned
Before lab 2, I did not know how to build and run a server on my local computer. It was interesting to modify a code that takes in a url input and see how the statements returned can change based on the user input. It was insiightful to see how we can create a code that changes ouput by changing the path and query, such as we did with `/increment` in lab and `add-message?s=<string>` during this lab report. Before then, I never have used my code on an online server, so it was fun doing so! 
