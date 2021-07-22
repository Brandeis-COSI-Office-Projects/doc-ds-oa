---
title: "Collect"
weight: 5
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

# Steps to collect the data

## File format

In the beginning of the project, you might be given a Google Sheet or a CSV file to start. If it's a Google Sheet, just stick to it. If it's a CSV file, uploading it to Google Sheet and edit online for easier sharing and collaborating.

## Example of the file

Whether it's a Google Sheet or CSV, it might look like this:

| x | FIRST | LAST | ... | Initials |  |
| --- | --- | --- | --- | --- | --- |
| 1 | personAFirstName | personALastName | ... | TZ | First Pass |
| 2 | personBFirstName | personBLastName | ... | CH | Not Found |
| ... | ... | ... | ... | ... | ... |

In the table, some columns looks like this:

| Job1 | Job 1 years of service | Job2 | Job 2 years of service | ... | Job 10 | Job 10 years of service |
| --- | --- | --- | --- | --- | --- | --- |
| Senior Principal Engineer | 7y5m | Product Marketing | 12y | ... | Senior Software Engineer | 3y10m |
| VP Software Development | 2y7m | VP System Development | 2y | ... |  |  |

These are the columns that you should care about.

## How to collect the data

You will presumably be asked to collect the data from LinkedIn. There are two things you should notice on:

- When you are copying job titles, **make sure it's copied to the correct cell**. E.g., job titles like "Software Engineer" should not reside in column "Job 2 years of service".
- When you are copying job duration/years of service, make sure to **reformat the time** to `"xyxm"` format. `"xyxm"` represents x amount of years and x amount of months. E.g., 3 years 4 months will be represented as "3y4m" and 12 years will be represented as "12y"

For example, ***none*** of the following time format is accepted:

| Job1 | Job 1 years of service | Job2 | Job 2 years of service | ... | Job 10 | Job 10 years of service |
| --- | --- | --- | --- | --- | --- | --- |
| Senior Principal Engineer | 7 years 5 months | Product Marketing | 12 yrs | ... | Senior Software Engineer | 3 yr 10 mos |
| VP Software Development | 2 y 7 m | VP System Development | 2 years | ... |  |  |

{{< hint danger >}}
Keeping the time format exactly as directed is very important! Data processing and cleaning procedure will not check time format and it uses exactly `"xyxm"` format to proceed.
{{< /hint >}}

## How to download the data for processing

- If you are in Google Sheet, download it as a `csv` file, rename it as `raw.csv`. 
- If you are in a csv file, rename it as `raw.csv`

Then, upload & replace the `raw.csv` in the [raw data repository](https://github.com/Brandeis-COSI-Office-Projects/ds-raw-data/tree/main/data).

Lastly, download the `data` folder in the [raw data repository](https://github.com/Brandeis-COSI-Office-Projects/ds-raw-data/tree/main/data) as directed and put the `data` folder inside your cloned [alumni-analytics](https://github.com/Brandeis-COSI-Office-Projects/alumni-analytics) directory. 