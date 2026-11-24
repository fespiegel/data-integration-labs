# Task 3 · Mine half a million journal articles

Data downloaded with the commands from the lecture (slide 35).

## 1. Shape

### 1a. Column names of `2014-01_JA.tsv` with their numbers

```bash
head -n 1 2014-01_JA.tsv | tr "\t" "\n" | cat -n
```

```text
     1  File
     2  Creator
     3  Issue
     4  Volume
     5  Journal
     6  ISSN
     7  ID
     8  Citation
     9  Title
    10  Place Labe
    11  Language
    12  Publisher
    13  Date
```

**Answer:** The file has 13 columns.

### 1b. Which name is cut off?

No extra command needed, the answer is in the output of 1a.

**Answer:** Column 10 is cut off: "Place Labe" (probably "Place Label").

### 1c. Do all four TSV files have the same header?

```bash
head -n 1 *.tsv
```

```text
==> 2014-01-31_JA-africa.tsv <==
File	Creator	Issue	Volume	Journal	ISSN	ID	Citation	Title	Place Labe	Language	Publisher	Date

==> 2014-01-31_JA-america.tsv <==
File	Creator	Issue	Volume	Journal	ISSN	ID	Citation	Title	Place Labe	Language	Publisher	Date

==> 2014-01_JA.tsv <==
File	Creator	Issue	Volume	Journal	ISSN	ID	Citation	Title	Place Labe	Language	Publisher	Date

==> 2014-02-02_JA-britain.tsv <==
File	Creator	Issue	Volume	Journal	ISSN	ID	Citation	Title	Place Labe	Language	Publisher	Date
```

To check it exactly, I saved the header line of each file and compared the files with `diff`:

```bash
head -n 1 2014-01_JA.tsv > header_jan.txt
head -n 1 2014-01-31_JA-africa.tsv > header_africa.txt
head -n 1 2014-01-31_JA-america.tsv > header_america.txt
head -n 1 2014-02-02_JA-britain.tsv > header_britain.txt

diff header_jan.txt header_africa.txt
diff header_jan.txt header_america.txt
diff header_jan.txt header_britain.txt
```

```text
(no output)
```

**Answer:** Yes, all four files have the same header. `diff` prints nothing when two files are equal, so the three other headers are identical to the one in `2014-01_JA.tsv`.

### 1d. How many articles does each file contain?

```bash
wc -l *.tsv
```

```text
   13712 2014-01-31_JA-africa.tsv
   27392 2014-01-31_JA-america.tsv
  507732 2014-01_JA.tsv
    5375 2014-02-02_JA-britain.tsv
  554211 total
```

**Answer:** `wc -l` counts lines, and the first line of each file is the header, not an article. So the files contain 13,711 (africa), 27,391 (america), 507,731 (2014-01_JA) and 5,374 (britain) articles.

## 2. Missing values

```bash
cut -f 11 2014-01_JA.tsv |  # take column 11 (Language) from every line
  sort |                    # sort alphabetically so identical values are neighbours
  uniq -c |                 # merge identical neighbours and put the count in front
  sort -nr                  # sort by that count, largest first
```

```text
 403284 eng
  40155 fre
  36100
  28192 ger
      1 Language
```

**Answer:** 36,100 articles have no language (the line with a count and no value). The languages are English (403,284), French (40,155) and German (28,192). The line "Language" with count 1 is the header, not an article.
