# Week 3 Lab Report
This is the third lab report for CSE 15L that will cover material from lab 3  Search Commands.

## Search Commands for grep: grep -n, grep -v, grep -c, grep -w
---
## `grep -n`
> This command is helpful for finding lines or files where a specified string pattern is matched. I learned about it from the [DigitalOcean website : https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix).
---
**Example #1**
> Say I was a assigned to write an essay on Italy, its landmarks, and its history. I would want to search through the contents of `.written_2/` to find any files with the title containing the string "Italy", so I would use `grep -n "Italy"` in the following way:

```
[cs15lwi23abi@ieng6-203]:docsearch:488$ find written_2 > find-results.txt
[cs15lwi23abi@ieng6-203]:docsearch:489$ grep -n "Italy" find-results.txt > grep-n-results.txt
[cs15lwi23abi@ieng6-203]:docsearch:490$ cat grep-n-results.txt
83:written_2/travel_guides/berlitz1/HistoryItaly.txt
104:written_2/travel_guides/berlitz1/IntroItaly.txt
128:written_2/travel_guides/berlitz1/WhatToItaly.txt
149:written_2/travel_guides/berlitz1/WhereToItaly.txt
```

> After using the command `grep -n "Italy"` and storing those contents into a .txt file and opening it with the `cat` command, we see there are 4 files whose titles contain the string "Italy." 

---

**Example #2**
> Suppose I want to be more educated about the history of different countries and want to efficiently search for all the files in `.written_2/` that have a title containing the string "History." I would use `grep -n "History"` in the following way:

```
[cs15lwi23abi@ieng6-203]:docsearch:491$ find written_2 > find-results.txt
[cs15lwi23abi@ieng6-203]:docsearch:492$ grep -n "History" find-results.txt > grep-n-results2.txt
[cs15lwi23abi@ieng6-203]:docsearch:494$ cat grep-n-results2.txt 
71:written_2/travel_guides/berlitz1/HistoryDublin.txt
72:written_2/travel_guides/berlitz1/HistoryEdinburgh.txt
73:written_2/travel_guides/berlitz1/HistoryEgypt.txt
74:written_2/travel_guides/berlitz1/HistoryFWI.txt
75:written_2/travel_guides/berlitz1/HistoryFrance.txt
76:written_2/travel_guides/berlitz1/HistoryGreek.txt
77:written_2/travel_guides/berlitz1/HistoryHawaii.txt
78:written_2/travel_guides/berlitz1/HistoryHongKong.txt
79:written_2/travel_guides/berlitz1/HistoryIbiza.txt
80:written_2/travel_guides/berlitz1/HistoryIndia.txt
81:written_2/travel_guides/berlitz1/HistoryIsrael.txt
82:written_2/travel_guides/berlitz1/HistoryIstanbul.txt
83:written_2/travel_guides/berlitz1/HistoryItaly.txt
84:written_2/travel_guides/berlitz1/HistoryJamaica.txt
85:written_2/travel_guides/berlitz1/HistoryJapan.txt
86:written_2/travel_guides/berlitz1/HistoryJerusalem.txt
87:written_2/travel_guides/berlitz1/HistoryLakeDistrict.txt
88:written_2/travel_guides/berlitz1/HistoryLasVegas.txt
89:written_2/travel_guides/berlitz1/HistoryMadeira.txt
90:written_2/travel_guides/berlitz1/HistoryMadrid.txt
91:written_2/travel_guides/berlitz1/HistoryMalaysia.txt
92:written_2/travel_guides/berlitz1/HistoryMallorca.txt
159:written_2/travel_guides/berlitz2/Algarve-History.txt
163:written_2/travel_guides/berlitz2/Amsterdam-History.txt
167:written_2/travel_guides/berlitz2/Athens-History.txt
171:written_2/travel_guides/berlitz2/Bahamas-History.txt
175:written_2/travel_guides/berlitz2/Bali-History.txt
178:written_2/travel_guides/berlitz2/Barcelona-History.txt
181:written_2/travel_guides/berlitz2/Beijing-History.txt
184:written_2/travel_guides/berlitz2/Berlin-History.txt
191:written_2/travel_guides/berlitz2/Budapest-History.txt
194:written_2/travel_guides/berlitz2/California-History.txt
197:written_2/travel_guides/berlitz2/Canada-History.txt
199:written_2/travel_guides/berlitz2/CanaryIslands-History.txt
202:written_2/travel_guides/berlitz2/Cancun-History.txt
205:written_2/travel_guides/berlitz2/China-History.txt
208:written_2/travel_guides/berlitz2/Costa-History.txt
211:written_2/travel_guides/berlitz2/CostaBlanca-History.txt
213:written_2/travel_guides/berlitz2/Crete-History.txt
217:written_2/travel_guides/berlitz2/Cuba-History.txt
220:written_2/travel_guides/berlitz2/Nepal-History.txt
223:written_2/travel_guides/berlitz2/NewOrleans-History.txt
226:written_2/travel_guides/berlitz2/Poland-History.txt
228:written_2/travel_guides/berlitz2/Portugal-History.txt
231:written_2/travel_guides/berlitz2/PuertoRico-History.txt
234:written_2/travel_guides/berlitz2/Vallarta-History.txt
```
> After using the command `grep -n "History"` and storing those results in a .txt file and opening its contents, I see that there are 46 history files I can read up on!

---

## `grep -v`
> This command is useful for *excluding* lines or files that contain a specified string pattern. I learned about it from the [DigitalOcean website : https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix).
---

**Example #1**

>In this example, I use `grep -v` twice, to find the specific, general contents contained in the non-fiction directory. I use `grep -v "travel_guides"` once to filter out all the files found in the travel_guides directories, and again with `grep -v ".txt"` to filter out the txt files. 

```
[cs15lwi23abi@ieng6-203]:docsearch:499$ grep -v  "travel_guides" find-results.txt > grep-v-results.txt
[cs15lwi23abi@ieng6-203]:docsearch:501$ grep -v ".txt" grep-v-results.txt > grep-v-results-cont.txt
[cs15lwi23abi@ieng6-203]:docsearch:503$ cat grep-v-results-cont.txt
written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Rybczynski
```

> After using the `cat` command to open up the txt file where I stored the contents of the two resulting `grep -n` commands, I can much easier see what the general contents are contained in the non-fiction directory and assess that there are 6 historical figures to read about. 

---

**Example #2**
> In this example, I use `grep -v` three times to find files in the travel_guides directory that do not discuss what things you can do or what places you can go at the travel destinations provided. I use `grep -v "non-fiction"` once to filter out all the files found in the non-fiction directory, again with `grep -v "Intro"` to filter out the intros to travel destinations, and again with `grep- v "History"` to filter out all the files that discuss the history of the travel destinations.

```
[cs15lwi23abi@ieng6-203]:docsearch:511$ grep -v  "non-fiction" find-results.txt > grep-v-results2.txt
[cs15lwi23abi@ieng6-203]:docsearch:512$ grep -v  "Intro" grep-v-results2.txt > grep-v-results2-1.txt
[cs15lwi23abi@ieng6-203]:docsearch:513$ grep -v  "History" grep-v-results2-1.txt > grep-v-results2-2.txt
[cs15lwi23abi@ieng6-203]:docsearch:514$ cat grep-v-results2-2.txt
written_2
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIsrael.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMadrid.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
written_2/travel_guides/berlitz1/JungleMalaysia.txt
written_2/travel_guides/berlitz1/WhatToDublin.txt
written_2/travel_guides/berlitz1/WhatToEdinburgh.txt
written_2/travel_guides/berlitz1/WhatToEgypt.txt
written_2/travel_guides/berlitz1/WhatToFWI.txt
written_2/travel_guides/berlitz1/WhatToFrance.txt
written_2/travel_guides/berlitz1/WhatToGreek.txt
written_2/travel_guides/berlitz1/WhatToHawaii.txt
written_2/travel_guides/berlitz1/WhatToHongKong.txt
written_2/travel_guides/berlitz1/WhatToIbiza.txt
written_2/travel_guides/berlitz1/WhatToIndia.txt
written_2/travel_guides/berlitz1/WhatToIsrael.txt
written_2/travel_guides/berlitz1/WhatToIstanbul.txt
written_2/travel_guides/berlitz1/WhatToItaly.txt
written_2/travel_guides/berlitz1/WhatToJamaica.txt
written_2/travel_guides/berlitz1/WhatToJapan.txt
written_2/travel_guides/berlitz1/WhatToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhatToLasVegas.txt
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt
written_2/travel_guides/berlitz1/WhatToMadeira.txt
written_2/travel_guides/berlitz1/WhatToMalaysia.txt
written_2/travel_guides/berlitz1/WhatToMallorca.txt
written_2/travel_guides/berlitz1/WhereToDublin.txt
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
written_2/travel_guides/berlitz1/WhereToEgypt.txt
written_2/travel_guides/berlitz1/WhereToFWI.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToGreek.txt
written_2/travel_guides/berlitz1/WhereToHawaii.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToIbiza.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToIsrael.txt
written_2/travel_guides/berlitz1/WhereToIstanbul.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhereToJerusalem.txt
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
written_2/travel_guides/berlitz1/WhereToMadeira.txt
written_2/travel_guides/berlitz1/WhereToMadrid.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz1/WhereToMallorca.txt
written_2/travel_guides/berlitz2
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2/travel_guides/berlitz2/Bali-WhatToDo.txt
written_2/travel_guides/berlitz2/Bali-WhereToGo.txt
written_2/travel_guides/berlitz2/Barcelona-WhatToDo.txt
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
written_2/travel_guides/berlitz2/Beijing-WhereToGo.txt
written_2/travel_guides/berlitz2/Berlin-WhatToDo.txt
written_2/travel_guides/berlitz2/Berlin-WhereToGo.txt
written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt
written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt
written_2/travel_guides/berlitz2/Bermuda-history.txt
written_2/travel_guides/berlitz2/Boston-WhereToGo.txt
written_2/travel_guides/berlitz2/Budapest-WhatToDo.txt
written_2/travel_guides/berlitz2/Budapest-WhereoGo.txt
written_2/travel_guides/berlitz2/California-WhatToDo.txt
written_2/travel_guides/berlitz2/California-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/CanaryIslands-WhatToDo.txt
written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt
written_2/travel_guides/berlitz2/China-WhatToDo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
written_2/travel_guides/berlitz2/Costa-WhatToDo.txt
written_2/travel_guides/berlitz2/Costa-WhereToGo.txt
written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt
written_2/travel_guides/berlitz2/Crete-WhatToDo.txt
written_2/travel_guides/berlitz2/Crete-WhereToGo.txt
written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt
written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt
written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt
written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt
written_2/travel_guides/berlitz2/Nepal-WhereToGo.txt
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
> Now, I can better access the files that contain places to go and things to do. 

---

## `grep -c`
> This command is useful for counting the lines or files that contain a specified string pattern. I learned about it from the [DigitalOcean website : https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix](https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix).
---
**Example #1**
>In this example, suppose I use `grep -c "WhereToGo` to find how many files contain the string "WhereToGo" in their titles to assess how many files I would need to skim before finally deciding where to travel to.

```
[cs15lwi23abi@ieng6-203]:docsearch:516$ grep -c "WhereToGo" find-results.txt
24
```
> I see there are 24 files in `./written_2` that I can skim to decide my travel destination!

---

**Example #2**

>In this example, I finally decided that I want to visit Canadaa, but I want to see how many files are in `./written_2` that talk about the country. I would use `grep -c "Canada"` to count how many files contain the string "Canada" in their titles to see how many sources I can absorb.

```
[cs15lwi23abi@ieng6-203]:docsearch:515$ grep -c "Canada" find-results.txt                     
2
```

> I learn that there are only two files containing the string "Canada" in `./written_2`.

---

## `grep -w`
> This command is useful for find matches of an *entire* and *exact* string pattern. I learned about it from the [GeeksForGeeks website : https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/).
---

**Example #1**
> After noticing the general pattern of the titles of the txt files found in `./written_2`, I want to see if there is a file that exists in the directory called `WhereToHawaii.txt`. In this example, I use the command `grep -w "WhereToHawaii.txt"` to help. 

```
[cs15lwi23abi@ieng6-203]:docsearch:502$ grep -w "WhereToHawaii.txt" find-results.txt
written_2/travel_guides/berlitz1/WhereToHawaii.txt
```
> After running the command, I do see that there is an exact match, so this file does indeed exist within the directory!

--- 

**Example #2**
> Learning that the non-fiction directory contains texts regarding historical figures, I want to see if there is an electronic book that exists in this directory for American civil rights activist Ralph Abernathy. I notice that the files are titled by last name, so I simply use the command `grep -w "Abernathy"` to help.

```
[cs15lwi23abi@ieng6-203]:docsearch:501$ grep -w "Abernathy" find-results.txt
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
```
> I discover that there is indeed a whole directory with text files about him!





