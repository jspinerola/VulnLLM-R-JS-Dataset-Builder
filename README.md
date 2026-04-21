# VulnLLM-R-JS-Dataset-Builder

Contribution to VulnLLM-R. Maps existing CVEfixes dataset to one supported by VulnLLM-R. For CSCI 4321 course at Texas A&amp;M University-San Antonio

## Getting Started

Not included in this project is the actual dataset source. Our source data is [CVEfixes by the secureIT Project](https://github.com/secureIT-project/CVEfixes).

To run our dataset builder, first download the dataset and extract it into the root of this repository. From there, run the following command inside of the newly created CVEfixes folder:

```console
$ gzcat Data/CVEfixes_v1.0.8.sql.gz | sqlite3 Data/CVEfixes.db
```

This will create the SQLite database necessary for our program.
