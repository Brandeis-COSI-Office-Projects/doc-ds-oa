---
weight: 1
bookFlatSection: true
title: "Quickstart"
---

# Quickstart

## Prerequisites

- Python 3.9 or higher *(I think version < 3.9 should work fine, but I use 3.9, so it's advisable to keep the same Python version to avoid weird problems.)*
- Git
- Github/Github Desktop
- Any text editor or IDE. I suggest using Visual Studio Code

### Python Version

```zsh
python3 --version
```

If you do not have python installed or the version is incorrect, follow the [python official documentation](https://www.python.org) to install/upgrade.

### Git Version

```zsh
git --version 
```

If you do not have git installed, please follow the [git official documentation](https://git-scm.com) to install Git. If you are using Windows, try to use [Git Bash](https://git-scm.com/downloads).

### Github Desktop

If you are fine using command line to control Github, great! If you are not comfortable using command line, please go ahead and download [Github Desktop](https://desktop.github.com).

## Repository

The repository should reside in the [Brandeis-COSI-Office-Projects](https://github.com/Brandeis-COSI-Office-Projects) organization. If you don't have access to it, please contact the Department Staff.

The repository name is: `alumni-analytics`

### Download

1. Please clone the repository to your local computer using either command line or Github Desktop.
2. Please download the `data` folder from the team. It should reside in a Google Drive folder. Please contract the Department Staff if you don't have access to it.
3. Put the `data` folder inside the project directory.

## Do a Quick Run

Run

```zsh
python3 code/main.py
```

{{< hint info >}}
**main.py**  
Run `main.py` will do the data extraction, cleaning, and processing. You can see the whole process displayed in the terminal. Final results will be generated in the `data` folder.
{{< /hint >}}