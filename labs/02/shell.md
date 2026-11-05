# Task 1 · Get to know your shell

## 1. Which shell?

**Command:**

```bash
echo $0
```

**Output:**

```
/usr/bin/bash
```

**Command:**

```bash
bash --version
```

**Output:**

```
GNU bash, version 5.3.15(2)-release (x86_64-pc-cygwin)
Copyright (C) 2025 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://www.gnu.org/licenses/gpl.html>

This is free software; you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
```

**Answer:** My terminal runs bash (`/usr/bin/bash`) in version 5.3.15.

## 2. Where am I?
**Command:**

```bash
cd ~/Downloads && pwd
```

**Output:**

```
/c/Users/finns/Downloads
```

**Answer:** My home directory is `/c/Users/finns` and my downloads folder is `/c/Users/finns/Downloads`. In File Explorer they appear as `C:\Users\finns` and `C:\Users\finns\Downloads`, which is the same location written in Windows style.

## 3. Where do commands come from?
**Command**

```bash
$  echo $PATH
```

**Output**

```bash
/c/Users/finns/bin:/ucrt64/bin:/usr/local/bin:/usr/bin:/bin:/ucrt64/bin:/usr/bin:/c/Users/finns/bin:/c/Program Files (x86)/NVIDIA Corporation/PhysX/Common:/c/WINDOWS/system32:/c/WINDOWS:/c/WINDOWS/System32/Wbem:/c/WINDOWS/System32/WindowsPowerShell/v1.0:/c/WINDOWS/System32/OpenSSH:/c/Program Files (x86)/Windows Kits/8.1/Windows Performance Toolkit:/c/Program Files (x86)/Microsoft SQL Server/160/Tools/Binn:/c/Program Files/Microsoft SQL Server/160/Tools/Binn:/c/Program Files/Microsoft SQL Server/Client SDK/ODBC/170/Tools/Binn:/c/Program Files/Microsoft SQL Server/160/DTS/Binn:/c/Program Files/dotnet:/cmd:/c/Users/finns/AppData/Local/Microsoft/WindowsApps:/c/Users/finns/AppData/Local/Python/bin:/c/Users/finns/AppData/Local/Programs/Microsoft VS Code/bin:/c/Users/finns/AppData/Local/GitHubDesktop/bin:/c/Users/finns/.lmstudio/bin:/usr/bin/vendor_perl:/usr/bin/core_perl
```

## 4. Where do commands come from?
**Command**

```bash
which curl
```

**Output**

```bash
/ucrt64/bin/curl
```

**Command**

```bash
which python3
```

**Output**

```bash
/c/Users/finns/AppData/Local/Microsoft/WindowsApps/python3
```
**Command**

```bash
$ which git
```

**Output**

```bash
/ucrt64/bin/git
```

**Command**

```bash
$ git --version
```

**Output**

```bash
git version 2.56.0.windows.4
```

**Answer:** Commands come from the directories listed in the `$PATH` environment variable, which the shell searches in order, running the first match it finds. There are 28 entries, 25 of them distinct (`/c/Users/finns/bin`, `/ucrt64/bin` and `/usr/bin` each appear twice, which is harmless because the first match wins). The first directory searched is `/c/Users/finns/bin`.

Locations of the programs (found with `which`):

- `curl`: `/ucrt64/bin/curl`
- `git`: `/ucrt64/bin/git`
- `python3`: `/c/Users/finns/AppData/Local/Microsoft/WindowsApps/python3`
-`git --version` prints `git version 2.56.0.windows.4`

### 5. How full is your disk?

Command

```bash
$ df -h
```

Output

```bash
Filesystem            Size  Used Avail Use% Mounted on
C:/Program Files/Git  457G  358G  100G  79% /
```

Command

```bash
$ du -sh ~/Downloads
```

Output

```bash
22G     /c/Users/finns/Downloads
```

Answer: The disk is 79% full: 358 GB of 457 GB are used and 100 GB are still free. The Downloads folder (`/c/Users/finns/Downloads`) takes up 22 GB, which is about 5% of the whole disk.
