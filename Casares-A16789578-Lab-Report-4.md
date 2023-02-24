# Lab Report 4
This is the fourth lab report for CSE 15L that will cover material from lab 7, CSE Labs "Done Quick."

## Shortcuts to Minimize Time
> This lab report is meant to describe the tricks/shortcuts we used during the lab competition. There were 6 total steps, not counting the setup (unforking and forking) and previous practice runs: 
1. Log into ieng6
2. Clone your fork of the repository from your Github account
3. Run the tests, demonstrating that they fail
4. Edit the code file to fix the failing test
5. Run the tests, demonstrating that they now succeed
6. Commit and push the resulting change to your Github account (you can pick any commit message!)
---

## Step 1: Log into ieng6

> To log into ieng6, the keys pressed were `<up><enter>`
After generating an SSH key for ieng6, I no longer have to enter my password.
My login for `ssh cs15lwi23abi@ieng6.ucsd.edu` was 1 command up in the history, so I used the `<up>` key once to access it to save time, then pressend `<enter>` and did not have to enter a password.

---

## Step 2: Clone your fork of the repository from your Github account
```
After forking the `lab7` repository and obtaining the link to the GitHub ssh link, I entered `git clone git@github.com:cacasares/lab7.git` into the terminal and pressed `<enter>`.

The command `git clone` clones a repository when a url follows it.
```
---

## Step 3: Run the tests, demonstrating that they fail
```
keys/commands entered: 
`cd lab7`
`<up><up><up><up><up><up><up><enter>`
The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was 7 up in the search history, so I used up arrow 7 times to access it.
`<up><up><up><up><up><up><up><up><up><up><up><up><enter>`
The `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` command was 10 up in the search history, so I used up arrow 10 times to access it.
```
The output was: 
```
FAILURES!!!
Tests run: 1,  Failures: 1
```

---

## Step 4: Edit the code file to fix the failing test
```
keys/commands entered: 
`<up><up><up><up><up><up><up><up><up><up><up><up><enter>`
The `nano ListExamples.java` command was 12 up in the search history, so I used up arrow 12 times to access it.
`<down> x 42 <right> x 12 <delete> <2>`
The bug was 42 lines down, 12 charcters right, where `index1 +=1` should instead be `index2 +=1`.
`<ctrl><o>, <enter>, <ctrl><x>`
The `<ctrl><o>` command saves changes, while the `<ctrl><x>` command exits `nano`.
```
---

## Step 5: Run the tests, demonstrating that they now succeed
```
keys/commands entered: 
`<up><up><up>><enter>`
The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was 3 up in the search history, so I used up arrow 3 times to access it.
`<up><up><up><enter>`
The `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` command was 3 up in the search history, so I used up arrow 3 times to access it.
```
The output was: 
```
JUnit version 4.13.2
..
Time: 0.014

OK (2 tests)
```

---

## Step 6: Commit and push the resulting change to your Github account (you can pick any commit message!)

```
keys/commands entered: 
<up><up><up><up><up><up><up><up><up><up><up><up><enter>
The `git add ListExamples.java` command was 12 up in the search history, so I used up arrow 12 times to access it. git add adds the changes to the file to the working directory, which is what needs to be done after I made the appropriate edits on the ListExamples.java file.

<up><up><up><up><up><up><up><up><up><up><up><up><enter>
Likewise, the `git commit -m "Fixed bug in ListExamples.java` command was 12 up in the search history, so I used up arrow 12 times to access it. git commit *commits* the change made, while the message in quotes is meant to describe the changes the editor made.

Finally, the `git push "a` command was 12 up in the search history, so I used up arrow 12 times to access it. git push uploads the local changes to your remote repository, so now, the changes I made in the `ListExamples.java` file can be seen on my repository online on my GitHub account. 

