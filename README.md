# Exploring Bias in Wikipedia's Political Articles by Country

## Goal
This repository contains all files required for Human Centered Data Science's (DATA 512) "Assignment 2: Bias in Data." More information about the assignment is available [here](https://wiki.communitydata.cc/Human_Centered_Data_Science_(Fall_2018)/Assignments#A2:_Bias_in_data).

The purpose of this assignment is to explore potential biases in Wikipedia’s political coverage by country. I explore this using two metrics:
* __Coverage__: The percent of political articles per country population.
* __Quality__: The percent of high-quality political articles per country's total political articles. 

Article quality will be determined using a machine learning algorithm called _Objective Revision Evalution Service_ ([ORES](https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model)).  This algorithm predicts between the following options:
* FA - Featured article
*	GA - Good article
*	B - B-class article
*	C - C-class article
*	Start - Start-class article
*	Stub - Stub-class article

A high-quality article will be ones considered either a _Freatured Article (FA)_ or a _Good Article (GA)_. The highest 2 of Wikipedia's 6 article quality options.

Then I reported and reflected on the highest and lowest ranked countries for each metric for potential bias. The [Jupyter Notebook](https://github.com/mag3141592/data-512-a2/blob/master/hcds-a2-bias.ipynb) will walk you through the full analysis.

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
After merging together the population data, Wikipedia page data, and the predicted page qualities I outputted this [dataset](https://github.com/mag3141592/data-512-a2/blob/master/data/hcds-a2-bias-data.csv).

| Column | Datatype |
| --- | --- |
| country | String |
| article_name | String |
| revision_id | Integer|
| article_quality | String |
| population | Integer|

## Reproducibility
This work is aimed at being reproducible, however due to data licensing and changes in page quality (from ORES's output) exact values may differ.  In order to fully reproduce the embedded figures, you'll need to import the merge dataset I provided and preform the steps after that file creation in the Jupyter Notebook. The merged dataset was created with the data available on 10/31/2018.

## Reflection

When first starting this assignment, I assumed there would be unequal political coverage globally for multiple reasons.  One assumption I had was based on internet access availability, whether from censorship or infrastructure, not being uniform.  This assumption would assume higher political article coverage in more developed countries and countries without internet censorship.  Another thing I had expected to find was a bias from that fact that a large fraction of English Wikipedia’s editors are from the US, Canada, Europe, and Australia.  I thought this would translate to higher coverage in the countries where the prevalence of editors in high, or even the countries those countries have a lot of political interest in.  Additionally, I assumed countries with larger government systems would have larger article counts and lower counts in countries with smaller political systems (democracy vs. dictatorship or monarchy). Lastly, I didn’t really know what biases to assume regarding quality coverage after reading about the ORES quality model which says quality is based on structural components not tone and good writing.  Although it does say that structural quality does correlate with good writing. 

In the analysis I wasn't able to analyze all 195 countries, instead I only used the 180 countries we had both population and article data for. Given more time I would have liked to identify the missing countries to see which were excluded and if that pointed to anything. The top ten countries for political coverage were all countries near Australia and Europe which supports my idea that the areas of higher concentration of editor would have higher coverage.  Then the ten lowest ranked countries for coverage were in Asia and Africa which both have a low prevalence of editors (except India), again supporting my original assumption.  India accounts for 3% of English Wikipedia editors, however they were ranked the lowest for coverage.  This I imagine, is due to its large population.

One result I was surprised to see was that the United States wasn’t in the top ten in coverage.  The United States only has 1098 political articles total.  Given that our current House of Representatives is 435 people, this count seems surprisingly low. One follow-up question I had was what qualifies as a political article (i.e. would local area Governor articles count)? I don't think my original government size theory holds much water after the analysis, considering it would more likely be related to government size in comparison with population size.

North Korea, Saudi Arabia and the United States were in the top ten in quality and of the 180 countries we have articles for, 36 had zero high-quality articles.  After removing those, the next lowest ten had about 1 high-quality article each. So the range of percent quality over the 180 countries was 0%  - 17.9%.  I was surprised that the top quality maxed out at 17.9 percent, because I would have assumed political articles tended to be more professional and well written.

With more time, I would have liked to explore the data graphically to better see trends and distributions because it is hard to theorize from short lists.

