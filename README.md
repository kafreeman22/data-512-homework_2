# data-512-homework_1
## Keegan Freeman
### 10/12/22

## Project Description
The goal of this project is to analyze bias present within Wikipedia articles and associate it with region, country, and population. The primary data science tasks present in this repo are as follows
1. Pulling data from Wikipedia using the MediaWiki API ([documentation](https://www.mediawiki.org/wiki/API:Main_page), [endpoint](https://www.mediawiki.org/w/api.php), [terms of use](https://foundation.wikimedia.org/wiki/Terms_of_Use/en), [license](https://www.mediawiki.org/wiki/Special:Version/License/MediaWiki)) on politician list to find revision id.
2. Pulling data from Wikipedia using ORES (part of MediaWiki) to find predicted article quality labels from previously pulled revision ids.
3. Merge population_by_country_2022.csv and politicians_by_country.SEPT.2022.csv and associate 'revision id' and 'article_quality'. Drop rows that resulted in error within API
4. Find quality articles per capita and quantity articles per capita for both region and country. Drop countries that resulted in calculation errors such as NaN or *inf*
5. Sort countries and regions by quality articles per capita and quantity articles per capita.
6. Display sorted results in tabular format

**Data note: As *"Identify all countries for which there are no matches and output a list of those countries"* is somewhat ambiguous, I interpreted this to mean the countries that resulted in error when calculating 'per capita' through either NaN or *inf***

## Files included
| File                                 | Description                                     |
| ------------------------------------ | ----------------------------------------------- |
| HW2.ipynb                            | Notebook of Data Analysis                       |
| wp_countries-no_match.txt            | Contains countries unable to analyze            |
| wp_politicians_by_country.csv        | Contains cleaned politician and population data |
| population_by_country_2022.csv       | Contains list of regions and countries by pop   |
| politicians_by_country.SEPT.2022.csv | Contains list of politicians for analysis       |

## Schema of wp_politicians_by_country.csv
| Column          |
| --------------- |
| country         |
| region          |
| population      |
| article_title   |
| revision_id     |
| article_quality |

## Research Implications
### What I have learned
### What I found
### What suprised me about my findings
### Theories about found biases

### Q/A
What biases did you expect to find in the data (before you started working with it), and why?

What (potential) sources of bias did you discover in the course of your data processing and analysis?

What might your results suggest about (English) Wikipedia as a data source?

What might your results suggest about the internet and global society in general?

Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?

Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might still be appropriate and useful, despite its inherent limitations and biases?

How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?
