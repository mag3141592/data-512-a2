# Exploring Bias in Wikipedia's Political Articles by Country

## Goal
This repository contains all files required for Human Centered Data Science's (DATA 512) "Assignment 2: Bias in Data." More information about the assignment is available [here](https://wiki.communitydata.cc/Human_Centered_Data_Science_(Fall_2018)/Assignments#A2:_Bias_in_data).

The purpose of this assignment is to explore potential biases in Wikipedia’s political coverage by country. I explore this using two metrics:
* __Coverage__: The percent of political articles per country population.
* __Quality__: The percent of high-quality political articles per country's total political articles. 

Article quality will be determined using a machine learning algorithm called _Objective Revision Evalution Service_ ([ORES](https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model).  This algorithm predicts between the following options:
* FA - Featured article
*	GA - Good article
*	B - B-class article
*	C - C-class article
*	Start - Start-class article
*	Stub - Stub-class article

A high-quality article will be one considered either a _Freatured Article (FA)_ or a _Good Article (GA)_. The highest 2 of Wikipedia's 6 article quality options.

Then I reported on reflected on the highest and lowest ranked countries for each metric. The [Jupyter Notebook]() will walk you through the full analysis.

## Directory
> data-512-a2/

| Filename | Purpose |
| --- | --- |
| data/... | Contains the outputted final merged dataset. |
| LICENSE | A standard MIT license. |
| README.md | What you're currently reading. |
| hcds-a2-bias.ipynb | The source code. |

## Data Acquistion
Two datasets were used in this analysis.
1. World Population Data available on [DropBox](https://www.dropbox.com/s/5u7sy1xt7g0oi2c/WPDS_2018_data.csv?dl=0).

| Column Name | Datatype |
| --- | --- |
| Geography | String |
| Population mid-2018 (millions) | String |

2. Wikipedia's Political Articles data available on [Figshare](https://figshare.com/articles/Untitled_Item/5513449).

| Column Name | Datatype |
| --- | --- |
| Page | String |
| Country | String |
| Rev_id | Integer|

## Licensing
The source datasets are not included in this repository due to the following licensing and copyright concerns.
1. The World Population dataset does not provide explicit licensing information, so it falls under DropBox's [copyright policy](https://www.dropbox.com/terms2016).
2. The Wikipedia page dataset on Figshare is licensed under CC-BY-SA 4.0.

The code in this repository is licensed under a [MIT](https://opensource.org/licenses/MIT) license.

## Output


## Reproducibility

## Results and Reflection


