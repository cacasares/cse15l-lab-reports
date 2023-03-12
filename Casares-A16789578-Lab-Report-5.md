# Lab Report 5
This is the last lab report for CSE 15L meant to reflect upon a past lab report. In this case, I will expand upon lab report 3, but instead of exploring `grep`, I will do the same exploration for different commands- `mv`, `touch`, and `whatis <command>`.

## `mv` command
> The mv command either moves a file to a different directory or renames it. 
Source: [IBM website : (https://www.ibm.com/docs/en/aix/7.1?topic=files-moving-renaming-mv-command](https://www.ibm.com/docs/en/aix/7.1?topic=files-moving-renaming-mv-command)

---

**Example #1**
> Say I opened the path `docsearch/written_2/travel_guides` and I used the `ls` command to see what files are there. I notice that there is a file named `WhatToUnknown.txt`. I use the `cat` command to read about it and learn it is about what to do in Japan. I now want to rename it.

```
[cs15lwi23abi@ieng6-203]:berlitz1:516$ ls
HandRHawaii.txt        HistoryEdinburgh.txt  HistoryLakeDistrict.txt  IntroIsrael.txt        WhatToEdinburgh.txt     WhatToLosAngeles.txt  WhereToIsrael.txt
HandRHongKong.txt      HistoryEgypt.txt      HistoryLasVegas.txt      IntroIstanbul.txt      WhatToEgypt.txt         WhatToMadeira.txt     WhereToIstanbul.txt
HandRIbiza.txt         HistoryFWI.txt        HistoryMadeira.txt       IntroItaly.txt         WhatToFWI.txt           WhatToMalaysia.txt    WhereToItaly.txt
HandRIsrael.txt        HistoryFrance.txt     HistoryMadrid.txt        IntroJamaica.txt       WhatToFrance.txt        WhatToMallorca.txt    WhereToJapan.txt
HandRIstanbul.txt      HistoryGreek.txt      HistoryMalaysia.txt      IntroJapan.txt         WhatToGreek.txt         WhatToUnknown.txt     WhereToJerusalem.txt
HandRJamaica.txt       HistoryHawaii.txt     HistoryMallorca.txt      IntroJerusalem.txt     WhatToHawaii.txt        WhereToDublin.txt     WhereToLakeDistrict.txt
HandRJerusalem.txt     HistoryHongKong.txt   IntroDublin.txt          IntroLakeDistrict.txt  WhatToHongKong.txt      WhereToEdinburgh.txt  WhereToLosAngeles.txt
HandRLakeDistrict.txt  HistoryIbiza.txt      IntroEdinburgh.txt       IntroLasVegas.txt      WhatToIbiza.txt         WhereToEgypt.txt      WhereToMadeira.txt
HandRLasVegas.txt      HistoryIndia.txt      IntroEgypt.txt           IntroLosAngeles.txt    WhatToIndia.txt         WhereToFWI.txt        WhereToMadrid.txt
HandRLisbon.txt        HistoryIsrael.txt     IntroFWI.txt             IntroMadeira.txt       WhatToIsrael.txt        WhereToFrance.txt     WhereToMalaysia.txt
HandRLosAngeles.txt    HistoryIstanbul.txt   IntroFrance.txt          IntroMadrid.txt        WhatToIstanbul.txt      WhereToGreek.txt      WhereToMallorca.txt
HandRMadeira.txt       HistoryItaly.txt      IntroGreek.txt           IntroMalaysia.txt      WhatToItaly.txt         WhereToHawaii.txt
HandRMadrid.txt        HistoryJamaica.txt    IntroHongKong.txt        IntroMallorca.txt      WhatToJamaica.txt       WhereToHongKong.txt
HandRMallorca.txt      HistoryJapan.txt      IntroIbiza.txt           JungleMalaysia.txt     WhatToLakeDistrict.txt  WhereToIbiza.txt
HistoryDublin.txt      HistoryJerusalem.txt  IntroIndia.txt           WhatToDublin.txt       WhatToLasVegas.txt      WhereToIndia.txt
[cs15lwi23abi@ieng6-203]:berlitz1:518$ mv WhatToUnknown.txt WhatToJapan.txt
[cs15lwi23abi@ieng6-203]:berlitz1:519$ ls
HandRHawaii.txt        HistoryEdinburgh.txt  HistoryLakeDistrict.txt  IntroIsrael.txt        WhatToEdinburgh.txt     WhatToLasVegas.txt    WhereToIsrael.txt
HandRHongKong.txt      HistoryEgypt.txt      HistoryLasVegas.txt      IntroIstanbul.txt      WhatToEgypt.txt         WhatToLosAngeles.txt  WhereToIstanbul.txt
HandRIbiza.txt         HistoryFWI.txt        HistoryMadeira.txt       IntroItaly.txt         WhatToFWI.txt           WhatToMadeira.txt     WhereToItaly.txt
HandRIsrael.txt        HistoryFrance.txt     HistoryMadrid.txt        IntroJamaica.txt       WhatToFrance.txt        WhatToMalaysia.txt    WhereToJapan.txt
HandRIstanbul.txt      HistoryGreek.txt      HistoryMalaysia.txt      IntroJapan.txt         WhatToGreek.txt         WhatToMallorca.txt    WhereToJerusalem.txt
HandRJamaica.txt       HistoryHawaii.txt     HistoryMallorca.txt      IntroJerusalem.txt     WhatToHawaii.txt        WhereToDublin.txt     WhereToLakeDistrict.txt
HandRJerusalem.txt     HistoryHongKong.txt   IntroDublin.txt          IntroLakeDistrict.txt  WhatToHongKong.txt      WhereToEdinburgh.txt  WhereToLosAngeles.txt
HandRLakeDistrict.txt  HistoryIbiza.txt      IntroEdinburgh.txt       IntroLasVegas.txt      WhatToIbiza.txt         WhereToEgypt.txt      WhereToMadeira.txt
HandRLasVegas.txt      HistoryIndia.txt      IntroEgypt.txt           IntroLosAngeles.txt    WhatToIndia.txt         WhereToFWI.txt        WhereToMadrid.txt
HandRLisbon.txt        HistoryIsrael.txt     IntroFWI.txt             IntroMadeira.txt       WhatToIsrael.txt        WhereToFrance.txt     WhereToMalaysia.txt
HandRLosAngeles.txt    HistoryIstanbul.txt   IntroFrance.txt          IntroMadrid.txt        WhatToIstanbul.txt      WhereToGreek.txt      WhereToMallorca.txt
HandRMadeira.txt       HistoryItaly.txt      IntroGreek.txt           IntroMalaysia.txt      WhatToItaly.txt         WhereToHawaii.txt
HandRMadrid.txt        HistoryJamaica.txt    IntroHongKong.txt        IntroMallorca.txt      WhatToJamaica.txt       WhereToHongKong.txt
HandRMallorca.txt      HistoryJapan.txt      IntroIbiza.txt           JungleMalaysia.txt     WhatToJapan.txt         WhereToIbiza.txt
HistoryDublin.txt      HistoryJerusalem.txt  IntroIndia.txt           WhatToDublin.txt       WhatToLakeDistrict.txt  WhereToIndia.txt
[cs15lwi23abi@ieng6-203]:berlitz1:520$ 
```
The file now has the appropriate name. 

---

**Example #2**
> I will now use this command to move a file to a different directory. Say I want to store the file `berlitz2_grep.txt` in `docsearch` into a more specific directory, `written_2/travel_guides/berlitz2/`. I would use `mv`.

---

Before:
```
[cs15lwi23abi@ieng6-203]:docsearch:532$ ls
DocSearchServer.class  README.md                TestDocSearch.class    berlitz1_sizes.txt  written_2
DocSearchServer.java   Server.class             TestDocSearch.java     berlitz2_grep.txt   lib
FileHelpers.class      Server.java              URLHandler.class       count-txts.sh       start.sh
Handler.class          ServerHttpHandler.class  berlitz1_grep.txtgrep  find-results.txt    test.sh
[cs15lwi23abi@ieng6-203]:docsearch:533$ mv berlitz2_grep.txt written_2/travel_guides/berlitz
[cs15lwi23abi@ieng6-203]:docsearch:533$ mv berlitz2_grep.txt written_2/travel_guides/berlitz2/
[cs15lwi23abi@ieng6-203]:docsearch:534$ 
```

---

After:
```
[cs15lwi23abi@ieng6-203]:berlitz2:539$ ls
Algarve-History.txt      Bahamas-WhatToDo.txt     Bermuda-WhatToDo.txt        CanaryIslands-WhereToGo.txt  Crete-WhereToGo.txt       Portugal-WhatToDo.txt
Algarve-Intro.txt        Bahamas-WhereToGo.txt    Bermuda-WhereToGo.txt       Cancun-History.txt           CstaBlanca-WhereToGo.txt  Portugal-WhereToGo.txt
Algarve-WhatToDo.txt     Bali-History.txt         Bermuda-history.txt         Cancun-WhatToDo.txt          Cuba-History.txt          PuertoRico-History.txt
Algarve-WhereToGo.txt    Bali-WhatToDo.txt        Boston-WhereToGo.txt        Cancun-WhereToGo.txt         Cuba-WhatToDo.txt         PuertoRico-WhatToDo.txt
Amsterdam-History.txt    Bali-WhereToGo.txt       Budapest-History.txt        China-History.txt            Cuba-WhereToGo.txt        PuertoRico-WhereToGo.txt
Amsterdam-Intro.txt      Barcelona-History.txt    Budapest-WhatToDo.txt       China-WhatToDo.txt           Nepal-History.txt         Vallarta-History.txt
Amsterdam-WhatToDo.txt   Barcelona-WhatToDo.txt   Budapest-WhereoGo.txt       China-WhereToGo.txt          Nepal-WhatToDo.txt        Vallarta-WhatToDo.txt
Amsterdam-WhereToGo.txt  Barcelona-WhereToGo.txt  California-History.txt      Costa-History.txt            Nepal-WhereToGo.txt       Vallarta-WhereToGo.txt
Athens-History.txt       Beijing-History.txt      California-WhatToDo.txt     Costa-WhatToDo.txt           NewOrleans-History.txt    berlitz2_grep.txt
Athens-Intro.txt         Beijing-WhatToDo.txt     California-WhereToGo.txt    Costa-WhereToGo.txt          Paris-WhatToDo.txt
Athens-WhatToDo.txt      Beijing-WhereToGo.txt    Canada-History.txt          CostaBlanca-History.txt      Paris-WhereToGo.txt
Athens-WhereToGo.txt     Berlin-History.txt       Canada-WhereToGo.txt        CostaBlanca-WhatToDo.txt     Poland-History.txt
Bahamas-History.txt      Berlin-WhatToDo.txt      CanaryIslands-History.txt   Crete-History.txt            Poland-WhatToDo.txt
Bahamas-Intro.txt        Berlin-WhereToGo.txt     CanaryIslands-WhatToDo.txt  Crete-WhatToDo.txt           Portugal-History.txt
```
The file is now in `berlitz2`.

> After using the command `grep -n "Italy"` and storing those contents into a .txt file and opening it with the `cat` command, we see there are 4 files whose titles contain the string "Italy." 

---

## `touch`
> This command creates an file.
Source: [GeeksforGeeks website: https://www.geeksforgeeks.org/touch-command-in-linux-with-examples/](https://www.geeksforgeeks.org/touch-command-in-linux-with-examples/)

---

**Example**
> Suppose I want to add a file "WhatToDoPhilippines.txt" to `travel_guides` after visiting the country.
I would first want to ensure I am in the correct directory, then create the file there. 
```
[cs15lwi23abi@ieng6-203]:berlitz2:540$ pwd
/home/linux/ieng6/cs15lwi23/cs15lwi23abi/docsearch/written_2/travel_guides/berlitz2
[cs15lwi23abi@ieng6-203]:berlitz2:541$ touch Philippines-WhatToDo.txt
[cs15lwi23abi@ieng6-203]:berlitz2:542$ ls
Algarve-History.txt      Bahamas-WhatToDo.txt     Bermuda-WhatToDo.txt        CanaryIslands-WhereToGo.txt  Crete-WhereToGo.txt       Portugal-History.txt
Algarve-Intro.txt        Bahamas-WhereToGo.txt    Bermuda-WhereToGo.txt       Cancun-History.txt           CstaBlanca-WhereToGo.txt  Portugal-WhatToDo.txt
Algarve-WhatToDo.txt     Bali-History.txt         Bermuda-history.txt         Cancun-WhatToDo.txt          Cuba-History.txt          Portugal-WhereToGo.txt
Algarve-WhereToGo.txt    Bali-WhatToDo.txt        Boston-WhereToGo.txt        Cancun-WhereToGo.txt         Cuba-WhatToDo.txt         PuertoRico-History.txt
Amsterdam-History.txt    Bali-WhereToGo.txt       Budapest-History.txt        China-History.txt            Cuba-WhereToGo.txt        PuertoRico-WhatToDo.txt
Amsterdam-Intro.txt      Barcelona-History.txt    Budapest-WhatToDo.txt       China-WhatToDo.txt           Nepal-History.txt         PuertoRico-WhereToGo.txt
Amsterdam-WhatToDo.txt   Barcelona-WhatToDo.txt   Budapest-WhereoGo.txt       China-WhereToGo.txt          Nepal-WhatToDo.txt        Vallarta-History.txt
Amsterdam-WhereToGo.txt  Barcelona-WhereToGo.txt  California-History.txt      Costa-History.txt            Nepal-WhereToGo.txt       Vallarta-WhatToDo.txt
Athens-History.txt       Beijing-History.txt      California-WhatToDo.txt     Costa-WhatToDo.txt           NewOrleans-History.txt    Vallarta-WhereToGo.txt
Athens-Intro.txt         Beijing-WhatToDo.txt     California-WhereToGo.txt    Costa-WhereToGo.txt          Paris-WhatToDo.txt        berlitz2_grep.txt
Athens-WhatToDo.txt      Beijing-WhereToGo.txt    Canada-History.txt          CostaBlanca-History.txt      Paris-WhereToGo.txt
Athens-WhereToGo.txt     Berlin-History.txt       Canada-WhereToGo.txt        CostaBlanca-WhatToDo.txt     Philippines-WhatToDo.txt
Bahamas-History.txt      Berlin-WhatToDo.txt      CanaryIslands-History.txt   Crete-History.txt            Poland-History.txt
Bahamas-Intro.txt        Berlin-WhereToGo.txt     CanaryIslands-WhatToDo.txt  Crete-WhatToDo.txt           Poland-WhatToDo.txt
[cs15lwi23abi@ieng6-203]:berlitz2:543$ nano Philippines-WhatToDo.txt 
[cs15lwi23abi@ieng6-203]:berlitz2:544$ cat Philippines-WhatToDo.txt 
The Philippines has plenty of activities available for visitors to do!
```

---

As we can see, I created the file `Philippines-WhatToDo.txt` and then used `nano` to edit the file. Now, it is added to the directory of travel guides. specifically `berlitz2`.

---

## `whatis <command>`
> The command `whatis <command>` describes commands and how to use them. 
Source: [Tech Republic website: https://www.techrepublic.com/article/16-terminal-commands-every-user-should-know/](https://www.techrepublic.com/article/16-terminal-commands-every-user-should-know/)

---

**Example**
> Here, I use the `whatis <command>` to remember how to use the commands we learned in class such as `grep` and `find` and other useful commands, such as `mv`.
```
[cs15lwi23abi@ieng6-203]:travel_guides:504$ whatis grep 
grep (1)             - print lines matching a pattern
grep (1p)            - search a file for a pattern
[cs15lwi23abi@ieng6-203]:travel_guides:505$ whatis find
find (1)             - search for files in a directory hierarchy
find (1p)            - find files
[cs15lwi23abi@ieng6-203]:travel_guides:506$ whatis mv
mv (1)               - move (rename) files
mv (1p)              - move files
[cs15lwi23abi@ieng6-203]:travel_guides:513$ whatis touch
touch (1)            - change file timestamps
touch (1p)           - change file access and modification times
[cs15lwi23abi@ieng6-203]:travel_guides:514$ whatis rm
rm (1)               - remove files or directories
rm (1p)              - remove directory entries
[cs15lwi23abi@ieng6-203]:travel_guides:515$ whatis find
find (1)             - search for files in a directory hierarchy
find (1p)            - find files
```

---

## As we can see, the additional commands I worked with are especially useful for creating new files, moving/renaming them, and learning the function of commands you may be unfamiliar with. 




