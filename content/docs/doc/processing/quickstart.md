---
title: "Quickstart"
weight: 101
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
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

The repository name is: [alumni-analytics](https://github.com/Brandeis-COSI-Office-Projects/alumni-analytics)

### Download

1. Please clone the repository to your local computer using either command line or Github Desktop.
2. Please download the `data` folder from the organization. It should reside in [this repository](https://github.com/Brandeis-COSI-Office-Projects/ds-raw-data).
3. Put the `data` folder inside the project directory.

Right now, the file directory should look exactly like:

    .
    ├── README.md
    ├── code
    │   ├── clean.py
    │   ├── console_controller.py
    │   ├── main.py
    │   ├── preprocessing.py
    │   ├── process.py
    │   └── title_merge.py
    └── data
        ├── algorithm.json
        └── raw.csv

## Do a Quick Run

Run

```zsh
python3 code/main.py
```

{{< hint info >}}
**main.py**  
Run `main.py` will do the data extraction, cleaning, and processing. You can see the whole process displayed in the terminal. Final results will be generated in the `data` folder.
{{< /hint >}}

{{< hint warning >}}
You have to include `code/` in your command, or the code won't work.

Run exactly as `python3 code/main.py`
{{< /hint >}}

## Check the results

After the initial run, if everything works well, the file directory should look like this:

    .
    ├── README.md
    ├── cache
    │   └── Jul-21-2021-960
    │       ├── merged_processed.json
    │       ├── merged_sorted_title.json
    │       ├── merged_title.json
    │       ├── processed.json
    │       ├── sorted_title.json
    │       └── title.json
    ├── code
    │   ├── __pycache__
    │   │   ├── clean.cpython-39.pyc
    │   │   ├── console_controller.cpython-39.pyc
    │   │   ├── handle_new.cpython-39.pyc
    │   │   ├── message_controller.cpython-39.pyc
    │   │   ├── preprocessing.cpython-39.pyc
    │   │   ├── process.cpython-39.pyc
    │   │   └── title_merge.cpython-39.pyc
    │   ├── clean.py
    │   ├── console_controller.py
    │   ├── main.py
    │   ├── preprocessing.py
    │   ├── process.py
    │   └── title_merge.py
    ├── data
    │   ├── algorithm.json
    │   └── raw.csv
    ├── log
    │   └── Jul-21-2021-960.txt
    └── result
        └── Jul-21-2021-960.json

{{< hint info >}}
It's okay if your file name isn't `Jul-21-2021-960`. `960` is a randomly-generated three-digit number and `Jul-21-2021` is the current date.
{{< /hint >}}

Open `result/Jul-21-2021-960.json` or whatever your file name is. 

This json file is the final result. You can just use it to do visualization or convert it to csv file.

*Now, let's dig deeper into what's behind the scene.*