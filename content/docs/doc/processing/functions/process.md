---
title: "Process"
weight: 3
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Process existing/new data

Process, as the name suggests, is processing and cleaning all the data you have. You need to have the `data` folder residing in the directory in order to proceed.

## Two situations

There are two situations leading you to encounter different things:

1. When you just want to process the old data to see what the result looks like;
2. When you have new grads' information to process

Let's start with the easier one: ***old data***.

### Just process the old data

After typing `p`, the following things will pop up:

    >> Entering process mode...

    - We are looking for raw.csv and algorithm.json file
    - Found!

    - Run a preprocessing step to make sure the data format is correct
        >> There are 1045 out of 1430 lines labelled as "First Pass",
        >>	so 1045 lines will be passed to the next round of real processing.
    - Preprocessing finished!

    [!Important] Please be aware that we will not check time format.
    - Make sure all of your job time is formatted as: xyxm or xy
        - [Hint: xyxm represents x amount of years and x amount of months. E.g., 3y4m]

    - Begin real processing
    - Processed!

    ......

    - Whole process finished!
    - Please view result/Jul-21-2021-926 folder to see the processed results
    - You can find cache files at cache/Jul-21-2021-926 folder

    [ -- See you next time! -- ]
    You can find console log file in log/Jul-21-2021-926.txt

And the following folders will be generated:

    cache/
    log/
    result/

#### Result json

Let's go to the `result` folder. That's where the final result resides in. There may be many `json` files if you run the program multiple times. Find the correct one by checking the file name for this run. In my case, it's `Jul-21-2021-926`.

You can just use this `json` for visualization or first convert it to `csv` and then do visualization. It has been processed and cleaned and ready for use.

> You can use **clean function** to clean up the `result` folder.

#### Cache

In the cache folder, there are a bunch of files that are generated during data processing. Normally, the folder should contain the following files:

    merged_processed.json
    merged_sorted_title.json
    merged_title.json
    processed.json
    sorted_title.json
    title.json

These files are:

processed.json
: the json file after initial extracting from csv; the version without processing and cleaning

title.json
: all the job titles with their occurrences, without processing and cleaning

sorted_title.json
: all the job titles sorted by their occurrences, without processing and cleaning

merged_processed.json
: the dictionary data file after merging job titles with the algorithm

merged_title.json
: all the job titles with their occurrences, after merging

merged_sorted_title
: all the job titles sorted by their occurrences, after merging

> You can use **clean function** to clean up the `cache` folder, as they are not quite important for visualization.

#### Log

`log/` contains all the output in console in case you forget about anything and you have closed the terminal.

> You can use **clean function** to clean up the `log` folder, as they are not quite important for visualization, only for your own purpose.

### Dealing with new data

If you have a bunch of new grads' information to process, you will encounter the "deal with new data" situation. Your console output might look like this:

    >> Entering process mode...

    - We are looking for raw.csv and algorithm.json file
    - Found!

    - Run a preprocessing step to make sure the data format is correct
        >> There are 1046 out of 1431 lines labelled as "First Pass",
        >>	so 1046 lines will be passed to the next round of real processing.

    [!Warning] We have seen some job titles that have not been seen/found/added to our algorithm.

    We have put all unseen job titles in pending/unseen_titles.txt
        1. Open pending/unseen_titles.txt and data/algorithm.json
        2. Determine which category(key) does each unseen job title in unseen_titles.txt belong to in algorithm.json
        3. Copy each unseen job title to the value array of corresponding category(key) in algorithm.json
        4. Rerun the program
    [ -- See you next time! -- ]
    You can find console log file in log/Jul-21-2021-912.txt

Most likely there will be some new, unseen job titles that are not included in the algorithm, like "professional dog walker" or "Java and Python and C++ developer". You should follow these steps to refine the algorithm:

1. Open `pending/unseen_titles.txt` file. It has a list of unseen job titles that you will add to the algorithm.
2. Open `data/algorithm.json`. The keys are job titles to stay because they are the most descriptive and have the most occurrences. The values are job titles to be merged because they are too subtle and only occur once or twice. 
{{< hint info >}}
For example, key-value pair like:
```json
"Software Engineer": [
    "Java Developer",
    "Software Architect"
    ......
]
```
Job titles like `Java Developer` and `Software Architect` will be replaced by `Software Engineer` because `Software Engineer` is more dominant in terms of occurrences and can describe what these two titles basically do.
For a more detailed explanation please visit [The Documentation for Staff](https://brandeis-cosi-office-projects.github.io/doc-ds-staff/docs/doc/process/clean-data/).
{{< /hint >}}
3. Determine which category(key) does each unseen job titles fall into. E.g., "Linux Engineer" falls into "Software Engineer" and "Marketing Research" falls into "Marketing".
4. Paste the unseen job title inside the value array of the corresponding category(key).
{{< hint info >}}
E.g., if previously the `algorithm.json` looks like this:
```json
"Software Engineer": [
    "Software Developer",
    "Developer",
    ......
]
......
```
And you determine that `Coder` also fall into this category. After pasting, it should look like this:
```json
"Software Engineer": [
    "Software Developer",
    "Developer",
    "Coder",
    ......
]
......
```
{{< /hint >}}
5. Save

After you finish with merging all the job titles, run `process` command again and watch what happens.