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

| Column | Datatype |
| --- | --- |
| Geography | String |
| Population mid-2018 (millions) | String |

2. Wikipedia's Political Articles data available on [Figshare](https://figshare.com/articles/Untitled_Item/5513449).

| Column | Datatype |
| --- | --- |
| page | String |
| country | String |
| rev_id | Integer|

## Licensing
The source datasets are not included in this repository due to the following licensing and copyright concerns.
1. The World Population dataset does not provide explicit licensing information, so it falls under DropBox's [copyright policy](https://www.dropbox.com/terms2016).
2. The Wikipedia page dataset on Figshare is licensed under CC-BY-SA 4.0.

The code in this repository is licensed under a [MIT](https://opensource.org/licenses/MIT) license.

## Output
After merging together the population data, Wikipedia page data, and the predicted page qualities I outputted this [dataset]().

| Column | Datatype |
| --- | --- |
| country | String |
| article_name | String |
| revision_id | Integer|
| article_quality | String |
| population | Integer|

## Reproducibility
This work is aimed at being reproducible, however due to data licensing and changes in page quality (from ORES's output) exact values may differ.  In order to fully reproduce the embedded figures, you'll be to import the merge dataset I created and preform the steps after it. The merged dataset was created with the data available on 10/31/2018.

## Reflection

1.	What biases did you expect to find in the data, and why? 
When first starting this assignment, I assumed there wouldn’t be equal political coverage globally for multiple reasons.  One assumption I had was based on internet access availability, whether from censorship or infrastructure, not being equal.  This assumption would assume higher political article coverage in more developed countries and countries without internet censorship.  Another thing I had expected to find was a bias from that fact that a large fraction of English Wikipedia’s editors are from the US, Canada, Europe, and Australia.  I thought this translated to higher coverage in those countries where the prevalence of editors in high, or even the countries those countries have a lot of political interest in.  Additionally, I assumed countries with larger government systems would have larger article counts and lower coverage in countries with smaller political systems (democracy vs. dictatorship or monarchy). I didn’t really know what biases to assume regarding quality coverage, after reading about the ORES quality model which says quality is based on structural components though those correlate with good writing. 
2.	What are the results?
In the analysis we weren’t able to analyze all 195 countries, instead we used the 180 countries we had population and article data for. The top ten countries for political coverage were all countries near Australia and Europe which supports my idea that the areas of high editor concentration would have higher coverage.  Then the lowest ranked ten countries for coverage were in Asia and Africa which have a low prevalence of editors (except India), again supported my original assumption.  One result I was surprised to see was that the United States wasn’t in the top ten in coverage.  The United States only has 1098 political articles total.  Given our House of Representatives is 435 people, this count seems surprising. So one follow-up question I had was what qualifies as a political article? 
North Korea, Saudi Arabia and the United States were in the top ten in quality. Of 180 countries we have articles for, 36 had zero high-quality articles. After removing those, the next lowest had about 1 high-quality article each. So the range over the 180 countries was 0  - 17.9, which I was surprised by that top number.
3.	What theories do you have about why the results are what they are?
India editors account 3% of English Wikipedia, however they were ranked the lowest for coverage.  This I imagine is due to its large population as well as its huge income inequality.  I don't think my original government size theory holds much water after the analysis, considering it would more likely be related to government size in comparison with population size.  With more time, I would have liked to explore the data graphically to better see trends and distributions because it is hard to theorize from short lists.

