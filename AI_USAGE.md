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
