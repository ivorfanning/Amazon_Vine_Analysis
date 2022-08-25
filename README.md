# Amazon_Vine_Analysis

The definition of big data is data that contains greater variety, arriving in increasing volumes and with more velocity. Because big data is larger, more complex data sets, especially from new data sources. These data sets are so voluminous that traditional data processing software just can’t manage them. We could use google colab and a python library pySpark to transform and munipulate the big data. We also need to use RDS provided by Amazon Web Services (AWS) to create a database instance and load the filtered big data into PostgreSql.

# Project Overview

In this project, we are using the sporting category in Amazon Review datasets to analyze if there is a bias towards reviews that were written as part of the Amazon Vine program

# Resources

- Amazon Review Datasets
- google colab
- Amazon Web Services, RDS
- pgAdmin

# Results

Firstly we need to install the pySpark library when using google colab notebook, and then download the reviews dataset. We chose sporting category to do the analysis. 

![sporting df](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/01%20sports%20df.png)

After seeing all the columns in sporting data frame, we filtered it into 4 different tables, and transform the filtered data into pgAdmin.

![customer table](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/02%20customer%20table.png)
![product table](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/03%20product%20table.png)
![reviews table](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/04%20reviews%20table.png)
![vine table](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/05%20vine%20table.png)

Next, we could proceed to analyze the last table which is the reviews written by the paid customers and unpaid customers.

In order to get a precise data, we need to eliminate the reviews data which are less than 20 reviews.
![more than 20 reviews](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/07%20reviews%20more%20than%2020%20and%20count.png)

and filtered out more helpful reviews data which are the helpful_votes are more than 50% of the total_votes.
![helpful votes](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/08%20helpful%20reviews%20and%20count.png)

The following analysis is for amazon paid vine program, we can tell from the next two images, the paid reviews are 334, and non paid reviews are 61614. From the numbers it is obvious that very less costomers are willing to pay for the vine program.
![paid reviews](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/09%20paid%20reviews%20and%20count.png)
![non paid reviews](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/10%20non%20paid%20reviews%20and%20count.png)

If we filtered the paid and non paid reviews by only 5 star rating, we could calculate the percentage of 5 star rating in total number of paid or non paid reviews.
![five star reviews](https://github.com/ivorfanning/Amazon_Vine_Analysis/blob/main/images/11%20five%20star%20calculation.png)

# Summary

The above images shows there is 42% five star reviews of the filtered paid reviews, and 53% five star reviews of the filtered non paid reviews. The percentage difference is 11%, so there is bias between the paid reviews and non paid reviews. However, the actual total number of paid reviews is much less than the total number of non paid reviews, we need more evidence or analysis to support our statement.

To further support the conclusion, we could redo the process on each star rating in the sporting category and see if there is a bias exists. Moreover, we could do analysis on every categories in the reviews datasets to evaluate the entire amazon vine program correctly.
