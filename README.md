# Amazon_Vine_Analysis

## Overview

The purpose of this project was to analyze Amazon reviews written by members of the Amazon Vine program, a service that allows manufacturers and publishers to receive reviews of their products.  This analysis set out to determine if there was any biases between Vine member and Non-Vine member reviews. 

In order to determine if there is any bias towards favourable reviews from Vine members vs. non-members, the percentage of 5 star rating as part of all ratings was calculated to determine if Vine members have a more favourable opinion of products reviewed compared to non-Vine members.

For this exercise, information from the “Electronics” category dataset was used to extract, transform and load customer review information into a dataframe in order to complete our analysis. The following tools were used during this analysis:

* `PySpark` to extract the dataset, transform the data, connect to `AWS RDS` instance and load the transformed data into `pgAdmin`.
* `Google Colaboratory` to import `PySpark` libraries and connect to `Postgres` in order to create `SQL` tables and export the results. 

## Results

For this analysis, one of fifty datasets was selected to conduct an initial analysis whose methodology could then be applied to the other category datasets.  The dataset chosen for this analysis was the “Electronics” category.  This dataset had over 3 million reviews recorded. In order to focus on reviews that would be considered more likely to be helpful, the dataset was filtered by:

* Count of Total Votes equal or greater than 20. 
* Percent of Helpful Votes to Total Votes equal or greater than 50%. 

![
](https://github.com/jbowman86/Amazon_Vine_Analysis/blob/eb483bd71d2ea7ecefc73b560408ba29e01b57ba/Images/Percentage_Vote.PNG)

The results reduced the total number of reviews from 3M to 50.7K. The filtered dataset was used to answer the following questions:

**1. How many Vine reviews and non-Vine reviews were there?**

* Vine members made up only 2.1% (1,080) of the reviews whereas the remaining 97.9% were Non-Vine members (49,659).

![
](https://github.com/jbowman86/Amazon_Vine_Analysis/blob/cf0453014a8eee9a1c81545dce147c7af5eacf49/Images/Vine_NonVine_Total.png)

![
](https://github.com/jbowman86/Amazon_Vine_Analysis/blob/cf0453014a8eee9a1c81545dce147c7af5eacf49/Images/Vine_Total_Reviews.png)

![
](https://github.com/jbowman86/Amazon_Vine_Analysis/blob/cf0453014a8eee9a1c81545dce147c7af5eacf49/Images/Non_Vine_Total_Reviews.png)

**2. How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?**

* Vine members gave 454 out of 1,080 reviews a 5 star rating.
* Non-Vine members gave 23,034 out of 49,659 reviews a 5 star rating.

**3. What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?**

* 42% of the reviews for Vine members were rated 5 stars.
* 46.4% of the reviews for Non-Vine members were rated 5 stars.

## Summary

Based on the results, Vine members did not show bias when rating their products considering that the number of 5-star ratings was about 10% less than Non-Vine members (42% vs. 46.4%). With this, it can be assumed that Vine customers are more critical when completing their reviews. However, in order to support this assumption further, the analysis should be completed including all of the data rather than filtering it to a percentage of helpful vs. total votes as was done for the current study.  Reviewing the unfiltered dataset provides more information and supplies further support for our assumptions.  The results of this preliminary analysis is shown below. 

![](https://github.com/jbowman86/Amazon_Vine_Analysis/blob/cf0453014a8eee9a1c81545dce147c7af5eacf49/Images/Non_Filtered_Total.png)

In addition, running the same analysis using datasets from different product categories can provide us with a greater understanding of whether reviews made by Vine members are biased.

