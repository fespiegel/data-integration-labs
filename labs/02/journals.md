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




