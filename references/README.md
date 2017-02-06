This directory contains data dictionaries and other documentation.

---

`CoTwinsDataModel_12_12_16.docx.pdf`

Documents the schema for both Michigan MySQL databases. Exported from Google Drive on December 12, 2016.

---

`phenx_column_labels`

Contains the column names and labels for `data/raw/Robin_PhenX_12-6-16.rds`, extracted using this mildly horrifying one-liner:

`Rscript -e 'library(readr);library(Hmisc);phenx <- read_rds("data/raw/Robin_PhenX_12-6-16.rds");label(phenx)' | xargs | sed 's/ PHXQ/;PHXQ/g' | tr ';' '\n' > references/phenx_column_labels`

xargs strips the white space, sed replaces the spaces between columns with semicolons, tr replaces the semicolons with newlines. I used this workaround because sed, at least on macOS, will not accept escaped newlines on the right hand side of the expression.