## 2026-10-27 · Lab 01, Task 1: profile README, icons

- **Tool and model:** Claude (claude.ai), Claude Sonnet 5.5 (effort: high)
- **Prompt:** "Give me links to fitting Icons in my following code: [my README draft], so that i can add them into it. Give me one example how to add a link, so its shown."
- **Output:** Links to icon badges (shields.io style) for my tech stack, and one example of how to embed an image link in Markdown.
- **Accepted / changed / rejected:** I accepted the badges for Python, SQL, R, GitHub and Microsoft Office and added them to my README.
- **How I checked it:** I opened my profile at github.com/fespiegel and saw that all five badges are displayed. A wrong link would show as a broken image, so I could check it directly.

## 2026-10-27 · Lab 01, Task 1: profile README, more professional

- **Tool and model:** Claude (claude.ai), Claude Sonnet 5.5 (effort: high)
- **Prompt:** "Give me tips to make my Readme look more professional"
- **Output:** Tips for improving the README, including a GitHub stats image (github-readme-streak-stats) with my user name.
- **Accepted / changed / rejected:** I kept the GitHub stats image from the first answer. I did not read the other tips, because I was satisfied with the first answer, so I did not use them.
- **How I checked it:** I opened my profile at github.com/fespiegel and saw that the stats image is displayed. I checked that the numbers belong to my own account (`user=fespiegel` in the link).

## 2026-10-30 · Lab 01, Task 4.2: What machines see (license check via GitHub API)

- **Tool and model:** Claude (claude.ai), Claude Sonnet 5.5 (effort: medium)
- **Prompt:** I asked for the correct path for `https://api.github.com/repos/OWNER/REPO` for my lab repo. Then I pasted the lab task and asked "Wie mache ich das zu: https://github.com/pandas-dev/pandas". Later I pasted the JSON for my lab repo and for owid/co2-data and asked: "Give me a summary to the licenses"
- **Output:** The API path `https://api.github.com/repos/fespiegel/data-integration-labs`, an explanation of how to find `spdx_id` under `license`, and draft one-sentence explanations for the three results. Claude also guessed that owid/co2-data would be `CC-BY-4.0`.
- **Accepted / changed / rejected:** I kept the API path and the explanation of how to read the `license` block. I rewrote the one-sentence explanations in my own words. I rejected the `CC-BY-4.0` guess, because the API returned `"license": null`.
- **How I checked it:** I opened all three API URLs in my browser and read the values myself: `BSD-3-Clause` (pandas-dev/pandas), `MIT` (fespiegel/data-integration-labs) and `null` (owid/co2-data).

## 2026-11-23 · Lab 02, Task 2: bashcrawl

I used Claude whenever I got stuck. I did not log every prompt, so these are representative examples.

* Tool and model: Claude (claude.ai), Claude Sonnet 5.5

**Entry 1: setup and paste errors**
* Prompt: I pasted the download and unzip commands and got `command not found` and endless `replace ...?` prompts from `unzip`. What went wrong?
* Output: Explanation of the bracketed-paste junk (`^[[200~`) and how pasted lines ran into the `unzip` prompt. Advice to cancel with Ctrl+C, delete the half-unpacked folder and type commands one at a time.
* Accepted / changed / rejected: Accepted. Later I also learned that pasting several lines at once breaks the game's y/n questions, so I typed commands by hand.
* How I checked it: `pwd` and `ls` showed the folders, and the game started correctly afterwards.

**Entry 2: understanding questions**
* Prompt: Why do I need `./treasure` and not `cd treasure`? What is a "program" here? Is Git the similar as Linux? What does `tree` do?
* Output: `cd` enters directories, `./` runs a script in the current directory because it is not in `$PATH`. Git is a version control tool, not an operating system. `tree` is not installed in Git Bash, so `find . | sort` is an alternative.
* Accepted / changed / rejected: Accepted. I compared the `$PATH` explanation with the "Where do commands come from?" slide of the lecture.
* How I checked it: `tree` really gave `command not found`, and `find . | sort` printed the map of the game.

**Entry 3: stuck in rooms (columbarium, padlock, robot)**
* Prompt: I pasted the output of the room and asked what to do next.
* Output: Hints to read the game code (`cat open`, `grep -v '^$' robot`), to use `sort room | uniq`, and a loop that tries all orders of alpha, beta, gamma, delta (result: `delta beta alpha gamma`).
* Accepted / changed / rejected: Accepted the columbarium (niche 15), the `uniq` trick and the loop. Rejected Claude's guess "Ravenscroft" for the padlock: the symbol F.K. means Frederick Kingsley (year 1765), so I corrected my inventory.
* How I checked it: `./padlock` showed whether the numbers were right, `sha256sum -c sha256sums` confirmed the robot order.

**Entry 4: log and submission**
* Prompt: How do I cut the history so it starts with my `cd` into `entrance`, what goes into `shell.md`?
* Output: `grep -n` and `tail -n +N` for the log, a draft of the `bashcrawl` section.
* Accepted / changed / rejected: The example line number `123` was wrong for my history (the log started mid-game), so I redid it with line 27. I chose three commands for `shell.md` that were not in the lecture (`export`, `let`, `ln -s`) after checking the lecture slides. I did not use a replay script Claude suggested. Lines 248 to 276 of the log come from an aborted attempt where I pasted several lines at once.
* How I checked it: `head` and `tail` of `bashcrawl.log`, and I opened both files on GitHub to confirm they are in `labs/02`.

## 2026-11-24 · Lab 2, Task 3, Question 1c (same header in all four TSV files?)

**Tool and model:** Claude (Claude Sonnet 5.5), claude.ai

**My own attempt first:** I wanted to compare the header lines of the four `.tsv` files. My idea was to look at the first line of every file with `head -n 1 *.tsv` and compare by eye.

**Prompt 1:** I asked whether `head -n 1 *.tsv` was the right idea for question 1c.
- Claude's answer: The command is correct and shows four identical-looking headers, but comparing by eye can miss small differences.
- What I did with it: I kept `head -n 1 *.tsv` and used its output as the first part of my answer.

**Prompt 2:** I then tried `head -n 1 | diff 2014-01-31_JA-africa.tsv 2014-01-31_JA-america.tsv` and it did not work, so I asked for help.
- Claude's answer: `diff` with two file names only reads those two files and ignores what comes through the pipe, so it would compare the whole files, not just the headers. It suggested saving each header line into its own new file with `head -n 1 ... > file` and comparing those files with `diff` (the approach from the hint "checking a claim").
- What I accepted: Saving the header of each file with `>` and comparing with `diff`. I compared `2014-01_JA.tsv` with the other three files.
- What I rejected or changed: I did not use `md5sum` or `diff <(...)`, because they are not in the course material. I also ran an earlier version with differently named helper files (`h_*.txt`) first.

**How I checked it:** `diff` printed nothing for all three comparisons, which according to the hint means the files are equal. This matches what I saw with `head -n 1 *.tsv`. I deleted the helper files afterwards.

## 2026-11-26 · Lab 2, Task 3, Question 3 (years)

**Tool and model:** Claude (Claude Sonnet 5.5), claude.ai

**My own attempt first:** I looked at the date format, counted the articles per year and found the year 2077 myself. My idea was to use `grep` to find the journal of the wrong year, and I tried `cut -f 13 | sort | uniq -c | grep "2077$"`.

**Prompt:** I asked whether my `grep` idea was right and how to find the journal.
- Claude's answer: The idea was right, but my command had already cut away the journal. Cut Journal and Date together, then search: `cut -f 5,13 2014-01_JA.tsv | grep "2077$" | sort | uniq -c`. Then search for the journal name to see its other years.
- What I accepted: Both commands. All 20 articles come from FRANCAIS DANS LE MONDE, whose other articles are from 1995 to 2013, so 2007 was probably meant.
- What I rejected or changed: Claude's first explanation of which digit differs between 2007 and 2077 was wrong. I corrected it: they differ in one digit. I also wrote "2077 lies in the future" instead of relying on the year 2014, which is only Claude's assumption from the file name.

**How I checked it:** I compared the year range of the journal with the possible one-digit changes of 2077.
