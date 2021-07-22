---
weight: "201"
---

# The code structure

Although the code are well-documented and structured, it is still worth explaining the overall structure for you to familiarize.

## code directory

The `code` directory looks like this:

    .
    ├── clean.py
    ├── console_controller.py
    ├── main.py
    ├── preprocessing.py
    ├── process.py
    └── title_merge.py

clean.py
: It will merge job titles based on the algorithm and unify time format to be xx.xx years.

console_controller.py
: It controls all the console output & recording.

main.py
: The execution program that will run processing and cleaning.

preprocessing.py
: Run the preprocessing step to make sure the data format is correct (only checks job titles).

process.py
: Extract the json information from csv file for cleaning.

title_merge.py
: Algorithm of merging job titles.

## data directory

Additionally, the `data` folder looks like this:

    .
    ├── algorithm.json
    └── raw.csv

algorithm.json
: It contains the algorithm to merge job titles.

raw.csv
: It contains the raw alumni data.