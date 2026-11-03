## **Part B Open-source**
### This repository (Task 4) looks inside an open source project more specific into [Pandas](https://github.com/pandas-dev/pandas).

### 1. License
The License names [BSD 3-Clause](https://github.com/pandas-dev/pandas/blob/main/LICENSE) as their license. It is permissive, not copyleft: it allows the code to be reused, modified, and redistributed, including in closed-source or commercial projects, and it does not require derivative works to be released under the same license.

If you copy code from the project into your own, you must:

- Keep the copyright notice, the list of conditions, and the disclaimer in any redistributed source code.
- Reproduce the same notice and disclaimer in the documentation or other materials if you distribute the code in binary form.
- Not use the names of the copyright holders or contributors (e.g. the pandas project) to endorse or promote your product without written permission.

### 2. What machines see
1. **pandas-dev/pandas**: The spdx_id is BSD-3-Clause, which tells a machine that pandas uses a permissive license: anyone may use, modify, and redistribute it as long as the copyright notice stays and the authors’ names aren’t used to promote derived products.
2. **My lab repo (fespiegel/data-integration-labs)**: The spdx_id is MIT, which tells a machine that my repo uses the permissive MIT License, so others may freely reuse and modify the code as long as they keep the copyright and license notice.
3. **owid/co2-data**: The license field is null, which means GitHub found no recognizable license file, so a machine reading the API sees no declared license and cannot tell whether reuse is permitted.

### 3. Community files

| File | Present? | Notes |
|------|----------|-------|
| `README` | ✅ Yes | Explains what the project is and how to use it |
| `LICENSE` | ✅ Yes | BSD-3-Clause, detected by GitHub |
| `CONTRIBUTING` | ✅ Yes | Describes how to help (issues, pull requests) |
| `CODE_OF_CONDUCT` | ✅ Yes | Contributor Covenant |

All four files are present, as shown under **Insights → Community standards**.
The repository also has a `SECURITY` file.

### 4. People

- **Contributors:** 3,889, as shown in the Contributors box on the repository
  page. Most of the work is done by a small core group; a lot of people
  contributed once (see Insights → Contributors for the distribution).
- **Who decides what gets merged:** the pandas **Core Team**. Only core team
  members can merge pull requests. Anyone can review, but merging needs a core
  member. The project works by consensus: no merging with an open objection,
  and larger changes should have approval from at least two core members.
  New core members are nominated and voted in by the existing Core Team after
  at least a year of sustained contributions.
- **Sources:** pandas governance page (pandas.pydata.org/about/governance.html)
  and the "pandas maintenance" guide in the contributor docs.

### 5. Money

- **Foundation:** pandas is a sponsored project of
  [NumFOCUS](https://numfocus.org), which acts as fiscal host on Open Collective
  and holds the money.
- **Donations and sponsors:** the repo's Sponsor link goes to
  [opencollective.com/pandas](https://opencollective.com/pandas), with backer
  ($5/month), sponsor ($100/month) and one-time donation options. The finances
  are public: about $310,900 raised in total, about $204,100 paid out, balance
  about $106,800 (as of 3 Nov 2026).
- **Grants:** Chan Zuckerberg Initiative grants appear as projects on the
  [Open Collective page](https://opencollective.com/pandas/projects).
- **Companies:** the [sponsors page](https://pandas.pydata.org/about/sponsors.html)
  lists sponsors (e.g. Tidelift, Bodo) and institutional partners that employ
  contributors (e.g. Nvidia).
- **Paid work:** the [expense list](https://opencollective.com/pandas/expenses)
  shows payments to contributors, e.g. a $9,450 "PR Review" payment in
  September 2026.
- **Volunteers:** most of the 3,889 contributors are probably volunteers.

**Sources:** [Open Collective](https://opencollective.com/pandas) ·
[Sponsors page](https://pandas.pydata.org/about/sponsors.html) ·
[Governance](https://pandas.pydata.org/about/governance.html)

### 6. Activity

- **Latest release:** [pandas 3.1.0](https://github.com/pandas-dev/pandas/releases/tag/v3.1.0),
  released on 22 October 2026. The project has 125 releases in total, and
  512 commits have landed on `main` since this one.
- **Open issues:** about 1.7k ([issues](https://github.com/pandas-dev/pandas/issues))
- **Open pull requests:** 295 ([pull requests](https://github.com/pandas-dev/pandas/pulls))
- *Checked on 3 Nov 2026.*

The project is very active: regular releases, hundreds of open pull requests
and a steady stream of commits.

### 7. Your way in

- **How a change gets in:** the [contributing guide](https://pandas.pydata.org/docs/dev/development/contributing.html)
  describes a fork-and-pull-request workflow: pick an issue and assign yourself,
  fork the repository, create a feature branch, make the change, open a pull
  request, address review comments, and a core team member merges it.
- **Newcomer label:** yes. The guide recommends issues labelled
  **good first issue** and **Docs**. Maintainers apply the label to
  well-defined, straightforward issues.
- **Number of open good first issues:** [read from Issues → Labels on [date]]
