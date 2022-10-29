# Amazon_Vine_Analysis

## Overview
The purpose of this analysis included the use of Amazon Web Services server and connecting an RDS to our local a postgres databased managed by PGAdmin locally. The idea was to use an S3 bucket dataset already provided, convert into a dataframe, transform the data by creating needed tables and load into the postgres database. Secondly to analyze a specific aspect of the customer data based on whether on they were paid or unpaid review services.

----
## Results

### Vine V/S Not Vine reviews

In order to determine how many vine and non vine reviews existed, it was fundamental to first narrow down the "helpful reviews". This was accomplished by filtering helpful_votes over total_votes in a ration of 50% and above, meaning that only reviews that the helpful reviews were more or equal than 50% would only be considered. 

![Screenshot](https://github.com/chgallegos/Amazon_Vine_Analysis/blob/main/resources/helpful_votes_ratio.png)

This meant that the amount of votes that were considered not helful were dropped, out of curiosity I calculated the amount by running the following code:

![Screenshot](https://github.com/chgallegos/Amazon_Vine_Analysis/blob/main/resources/dropped_votes.png)

Finnaly, the Vine and Non-Vine reviews were calculated by filtering the data and creating a dataframe for each condition.

#### Vine Reviews

![Screenshot](https://github.com/chgallegos/Amazon_Vine_Analysis/blob/main/resources/vine_votes.png)

#### Non-Vine Reviews

![Screenshot](https://github.com/chgallegos/Amazon_Vine_Analysis/blob/main/resources/non_vine_votes.png)


### Five Star Reviews and Percentages

In order to filter the five star reviews, the following code was used:

#### Vine Five Star Reviews
![Screenshot](https://github.com/chgallegos/Amazon_Vine_Analysis/blob/main/resources/vine_five.png)

#### Non-Vine Five Star Reviews
![Screenshot](https://github.com/chgallegos/Amazon_Vine_Analysis/blob/main/resources/not_vine_five.png)

## Summary 

The first thing that comes to mind when looking at the difference between Vine and Non-Vine data, is that given the high amount of difference of total reviews and the amount of five stars, one could infer that the data is biased towards having better (more star) reviews with using Vine. I am confident that my statement could be also supported if we add the "Verified purchase" part of the data to the analysis, meaning that if we remove Non verified purchases from the data, the analysis could be even more accurrate and less biased since the reviews would be made by customers that have been verified as well as with the intrinsic incentive genuine desire to review the product.