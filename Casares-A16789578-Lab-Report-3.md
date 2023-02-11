# Week 3 Lab Report
This is the third lab report for CSE 15L that will material from lab 3  Search Commands.

## Search Commands for grep: grep -n, grep -v, grep -c, grep -w
---
## `grep -n`
> This command is helpful for finding lines or files where a specified string pattern is matched.
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






