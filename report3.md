# Lab Report 3 - The `grep` Command (Week 5)

## 1. Search Recursively - The `-r` Flag

*Source: https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html#File-and-Directory-Selection*

### **Example 1:**
```
$ grep -r "Legos" written_2/non-fiction/OUP/Kauffman/ 
written_2/non-fiction/OUP/Kauffman//ch9.txt:My first purpose in investing in an entire box of Legos was to explore and define concepts of “robust constructibility.” We have succeeded, but run into fascinating problems of a general phase transition in problem solvability. In turn, this very phase transition suggests that in a coconstructing biosphere or econosphere rather specific restrictions arise and are respected by critters and firms, creatures and cognoscenti.
```
This command searches for the word `Legos` for each file in the directory `written_2/non-fiction/OUP/Kauffman/` by using the `-r` flag. The output of this command is one file, `written_2/non-fiction/OUP/Kauffman/ch9.txt`, and a portion from the matched text. Useful for finding files containing a particular string in a given directory.

<br>

### **Example 2:**
```
$ grep -rl "Poland" written_2/travel_guides/berlitz2/
written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
written_2/travel_guides/berlitz2/Berlin-History.txt
written_2/travel_guides/berlitz2/Poland-History.txt
```
This command searches for the word `Poland` for each file in `written_2/travel_guides/berlitz2/` by using the `-r` flag. In combination with the `-l` flag, the output of this command becomes a list of the files with the word "Poland" in it. Useful for finding matching files quickly.   

<br>

## 2. Match Whole Lines - The `-x` Flag

*Source: https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html#Matching-Control*

### **Example 1:**
```
$ grep -rx "WHERE TO GO" written_2/
written_2//travel_guides/berlitz2/Berlin-WhereToGo.txt:WHERE TO GO
written_2//travel_guides/berlitz2/Portugal-WhereToGo.txt:WHERE TO GO
written_2//travel_guides/berlitz2/Canada-WhereToGo.txt:WHERE TO GO
```
This command uses the `-r` flag to search for files in the `written_2/` directory. By using the `-x` flag, the output of this command is a list of matched files with the exact line, `WHERE TO GO`. Useful for narrowing a search down by using the file's title or heading.

<br>

### **Example 2:**
```
$ grep -rlx "Shopping" written_2/travel_guides/berlitz2/
written_2/travel_guides/berlitz2//Amsterdam-WhatToDo.txt
written_2/travel_guides/berlitz2//CostaBlanca-WhatToDo.txt
written_2/travel_guides/berlitz2//Cuba-WhatToDo.txt
written_2/travel_guides/berlitz2//Cancun-WhatToDo.txt
written_2/travel_guides/berlitz2//Berlin-WhatToDo.txt
written_2/travel_guides/berlitz2//Bermuda-WhatToDo.txt
written_2/travel_guides/berlitz2//Budapest-WhatToDo.txt
written_2/travel_guides/berlitz2//PuertoRico-WhatToDo.txt
written_2/travel_guides/berlitz2//Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2//Bali-WhatToDo.txt
written_2/travel_guides/berlitz2//Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2//Barcelona-WhatToDo.txt
written_2/travel_guides/berlitz2//Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2//Costa-WhatToDo.txt
written_2/travel_guides/berlitz2//Crete-WhatToDo.txt
written_2/travel_guides/berlitz2//CanaryIslands-WhatToDo.txt
written_2/travel_guides/berlitz2//California-WhatToDo.txt
written_2/travel_guides/berlitz2//China-WhatToDo.txt
written_2/travel_guides/berlitz2//Athens-WhatToDo.txt
written_2/travel_guides/berlitz2//Nepal-WhatToDo.txt
written_2/travel_guides/berlitz2//Paris-WhatToDo.txt
written_2/travel_guides/berlitz2//Beijing-WhatToDo.txt
```
This command uses the `-r` flag to recursively search through `written_2/travel_guides/berlitz2/` and the `-l` flag to limit the output to only matched files. The `-x` flag makes the command only match files which have the exact line, `Shopping`. Useful for finding files with certain headers.

<br>

## 3. Match Whole Words - The `-w` Flag

*Source: https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html#Matching-Control*

### **Example 1:**
```
$ grep -w "XV" written_2/travel_guides/berlitz1/HistoryFrance.txt 
        Louis XV. But government was in the hands of the late king’s cultured,
        The easy-going Louis XV was called the Bien-Aimé (Beloved),
        Louis XVI, grandson of Louis XV, found himself attacked on
```
This command uses the `-w` flag to search through the file `written_2/travel_guides/berlitz1/HistoryFrance.txt` and find matched lines containing only the whole word `XV`. Without the `-w` flag, mentions of Louis XVI or Louis XVII would have also been matched. This is useful for narrowing a search and ensuring exact whole word matches.

<br>

### **Example 2:**
```
$ grep -rlw "card" written_2/travel_guides
written_2/travel_guides/berlitz1/WhatToIbiza.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhatToMalaysia.txt
written_2/travel_guides/berlitz1/WhatToDublin.txt
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/IntroLasVegas.txt
written_2/travel_guides/berlitz1/WhereToJerusalem.txt
written_2/travel_guides/berlitz1/WhatToHongKong.txt
written_2/travel_guides/berlitz1/WhatToLasVegas.txt
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt
written_2/travel_guides/berlitz2/Berlin-WhereToGo.txt
written_2/travel_guides/berlitz2/Costa-WhereToGo.txt
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
written_2/travel_guides/berlitz2/NewOrleans-History.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2/Costa-WhatToDo.txt
written_2/travel_guides/berlitz2/Budapest-History.txt
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
```
This command uses the `-r` flag to search through the directory `written2/travel_guides/` and output a list of files (using `-l`) that match the whole word `card` (using `-w`). This is useful for limiting search results in a file with many similar words or substrings.

<br>

## 4. Case Insensitive Search - The `-i` Flag

*Source: https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html#Matching-Control*

### **Example 1:**
```
$ grep -ri "where to go" written_2/travel_guides/berlitz1/ 
written_2/travel_guides/berlitz1//HandRLasVegas.txt:        their casinos and attractions, look in Where To Go starting on page
written_2/travel_guides/berlitz1//WhereToGreek.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToLakeDistrict.txt:        Where To Go
written_2/travel_guides/berlitz1//WhereToIndia.txt:        Where to go
written_2/travel_guides/berlitz1//WhereToItaly.txt:        WHERE TO GO
written_2/travel_guides/berlitz1//WhereToMalaysia.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToJapan.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToEgypt.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToEdinburgh.txt:        Where To Go
written_2/travel_guides/berlitz1//WhereToIsrael.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToFrance.txt:        WHERE TO GO
written_2/travel_guides/berlitz1//WhereToDublin.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToMallorca.txt:        Where to go
written_2/travel_guides/berlitz1//WhereToMadeira.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToIbiza.txt:        •Where to Go
written_2/travel_guides/berlitz1//WhereToLosAngeles.txt:        Where to go
written_2/travel_guides/berlitz1//WhereToMadrid.txt:        WHERE TO GO
written_2/travel_guides/berlitz1//WhereToMadrid.txt:        the Plaza de Toros Monumental de Las Ventas. This is where to go to see
written_2/travel_guides/berlitz1//WhereToJerusalem.txt:        Where To Go
written_2/travel_guides/berlitz1//WhatToJamaica.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToHongKong.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToFWI.txt:        Where to Go
written_2/travel_guides/berlitz1//WhereToIstanbul.txt:        Where to go
written_2/travel_guides/berlitz1//WhatToLasVegas.txt:        “what to do” and “where to go” difficult to delineate. In Las Vegas,
```
This command uses the `-r` flag to search through `written_2/travel_guides/berlitz1/` and outputs a list of files that match the string `where to go`, regardless of case (using the `-i` flag). This is useful for making a case insensitive search by finding all instances of a substring.

<br>

### **Example 2:**
```
$ grep -wi "as" written_2/travel_guides/berlitz1/IntroMalaysia.txt
        As Malaysia has moved resolutely into the modern age, it has
        Water is also a constant presence, sometimes as waves lapping on white
        sandy beaches, or as beautiful cascading waterfalls, or as majestic,
        Even in Kuala Lumpur — as modern an urban sprawl as you
        peninsula. Malaysia rose first as a trading point for Asia and Europe,
        west like ribs, with one long north–south Main Range as their backbone.
        With the growth of tourism as a major industry, resort
        facilities have burgeoned in smaller islands such as Penang, Pangkor,
        unusual to find, as in old Melaka, Buddhist and Hindu temples on the
        same street as a mosque. Not least of all, it makes for a marvellous
        With Islam as the national religion and Malay — Bahasa
        Malaysia — as the national language, Malays enjoy practically exclusive
        bamboo industries. Just as court ritual is still colored by the ancient
        prove a necessity as the younger generation of business and community
```
This command uses the `-w` flag to find the whole word `as` in the file `written_2/travel_guides/berlitz1/IntroMalaysia.txt`. By also using the `-i` flag, the search for the word also becomes case insensitive. These flags are useful for making a case insensitive search for an exact word in a file.
