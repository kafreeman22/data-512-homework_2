# data-512-homework_2
## Keegan Freeman
### 10/12/22

## Project Description
The goal of this project is to analyze bias present within Wikipedia articles and associate it with region, country, and population. The primary data science tasks present in this repo are as follows
1. Pulling data from Wikipedia using the MediaWiki API ([documentation](https://www.mediawiki.org/wiki/API:Main_page), [endpoint](https://www.mediawiki.org/w/api.php), [terms of use](https://foundation.wikimedia.org/wiki/Terms_of_Use/en), [license](https://www.mediawiki.org/wiki/Special:Version/License/MediaWiki)) on politician list to find revision id.
2. Pulling data from Wikipedia using [ORES](https://www.mediawiki.org/wiki/ORES) (part of MediaWiki) to find predicted article quality labels from previously pulled revision ids.
3. Merge population_by_country_2022.csv and politicians_by_country.SEPT.2022.csv and associate 'revision id' and 'article_quality'. Drop rows that resulted in error within API
4. Find quality articles per capita and quantity articles per capita for both region and country. Drop countries that resulted in calculation errors such as NaN or *inf*
5. Sort countries and regions by quality articles per capita and quantity articles per capita.
6. Display sorted results in tabular format

**Data note: As *"Identify all countries for which there are no matches and output a list of those countries"* is somewhat ambiguous, I interpreted this to mean the countries that resulted in error when calculating 'per capita' through either NaN or *inf***

**Note: *Quality Article* refers to those receiving either "good article"* (GA) or *"featured article"* (FA) as a score.**

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

I've learned that Wikipedia articles are far more often updated or deleted in Wikipedia for the, what I assumed to be, dead website Wikipedia is. Discussing with multiple of my peers, as well as seeing the results change over the couple days webscraping, I found that a few articles were deleted as well as found revision ids to change. I've also learned that normalizing by capita heavily influnces the ranking of quality article quantity and article quantity by region and country in refernce to their non-normalized counterparts. 

### What I found

I've found the quantity of articles does **somewhat** coorelate to quality of articles. The ranked regions by quantity of articles does not deviate *very* far from them ranked by quantity of quality articles. Furthermore, I've found that Europe as a whole ranks fairly high in terms of both quantity and quality of articles whereas Africa ranks poorly. Next, it seems that quality, and quantity of articles, seem to coorelate to country wealth based on my understanding of country affluence.

### What suprised me about my findings

I was most suprised by the quantity of articles per capita of Japan due to it's affluence and pervasive culture. I was also suprised to see Vietnam ranking low in terms of coverage due to it being a major topic present within U.S. history. Finally, it is interesting to note that the Carribean ranks the highest in terms of quantity of quality articles despite it's lack of affluence.

### Theories about found biases

The theory I have regarding some of the suprising results found is that normalizing by capita shot places with a very small population and *normal* amount of articles much higher than those with a larger population. Secondly, as touched upon previously, my primary theory behind quality and quantity lies behind country affluence and wealth. Furthermore, as Wikipedia is a U.S. founded site, it makes sense that it would have a bias towards places more culturaly similear to the U.S. such as regions within Europe. This theory is backed by the lack of quantity and quality present for much of Africa and Asia. 

### Q/A
### What biases did you expect to find in the data (before you started working with it), and why?

I expected to see a bias leaning towards Europe primarily for the reasons mentioned above. Our exercise towards the end of our last class only bolstered this expectation seeing the clear bias Wikipedia has towards the United States. 

### What might your results suggest about (English) Wikipedia as a data source?

These results seem to indicate that Wikipedia is a fine resource for United States and European history; however, is not the most reliable regarding the rest of the world.

### What might your results suggest about the internet and global society in general?

Extrapolating on my findings, this would indicate that the internet/global society has a bias leaning towards the United States and Europe. This makes sense regarding the affluent media of both finding it's way across the globe. I must note; however, this is purly based on my findings specifically regarding Wikipedia articles. This bias most likely wildly fluctuates depending on the website used and its country of origin.

### Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?

This dataset would do an inadaquete job for the trained task for the regions/countries ranking lower in quality and quantity. This is reminiscent of our latest readings that describe the pitfalls of a dataset with limited scope for a group causing unintended issues such as racism and bias.

### Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might still be appropriate and useful, despite its inherent limitations and biases?

I would say that utilizing this dataset could be appropriate for an audience limited to those within Europe and the United States as well as a specific task geared towards those regions as well. 

### How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?

The most obvious solution I can think of is suplementing this dataset with other online encylipeidas with different countries of origins such to tip the balance of bias present.
