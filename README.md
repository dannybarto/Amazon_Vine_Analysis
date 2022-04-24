# Amazon_Vine_Analysis
#### *Analysis of Amazon's Vine review program using PySpark and AWS RDS with PostgreSQL*

## Overview

Selected U.S. Electronics review  for analysis. The ultimate objective is to determine if subscribing to the Vine program makes sense economically if we decided to sell similar products on Amazon. The Vine review program utilizes incentives to encourage user participation. Users are rewarded with "gifts" when they provide a positive review. I was able to use PySpark to extract, transform, and load (ETL) the data to a AWS *RDS* I created and connected to my PostgreSQL server to be able to query it and extract my finished tables from there. Part of the data transformation was made using pandas as well. 

The project featured the use of Spark. Spark is a unified analytics engine for large-sacale data processing.  

## Resources
- Datasets:
  - [U.S. Electronics Amazon Reviews dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Electronics_v1_00.tsv.gz)

- Technologies used:
  -  Google Colab (to run PySpark)
  -  AWS S3 and RDS 
  -  PostgreSQL
  - Jupyter Notebook

## Deliverable 1

1. Select dataset from "Amazon Review datasets" 
    - U.S. Electronics was selected for analysis
2. Create a new database with Amazon RDS 
3. In pgAdmin create a new database in your Amazon RDS server that you just created
4.  Download the "challenge_schema.sql" file to your computer
5. In pgAdmin run a new query to create the tables for your new database using the "challenge_schema.sql" file
    - After you run the query you will have the following four tables in the database:
      - "customers_table", "products_table", "review_id_table", and "vine_table"
6. Download the "Amazon_Reviews_ETL_starter_code.ipynb" file, then upload the file as Google Colab
    - Rename the file "Amazon_Reviews_ETL"
7. First extract one of the review datasets, then create a new DataFrame
8. Follow the steps below to transform the dataset into four DataFrames that will match the schema in the pgAdmin tables
    - 

Due to the size of the dataframes it took some time to load to PostgreSQL and the RDS. I then did a few quick queries to check that everything ran smoothly. 

<img width="745" alt="Screen Shot 2021-08-29 at 10 21 45 PM" src="https://user-images.githubusercontent.com/83378141/131558905-90cc438b-fd27-476c-808f-95096f8b9dcb.png">
<img width="743" alt="Screen Shot 2021-08-29 at 10 47 21 PM" src="https://user-images.githubusercontent.com/83378141/131558907-b7ba32fc-1752-4fcb-8d4f-9da12cac9ceb.png">
<img width="740" alt="Screen Shot 2021-08-29 at 11 21 27 PM" src="https://user-images.githubusercontent.com/83378141/131558908-a2c084ee-6702-42b7-9355-22e2bab1c772.png">
<img width="741" alt="Screen Shot 2021-08-29 at 11 25 19 PM" src="https://user-images.githubusercontent.com/83378141/131558909-3b5a6ef3-c351-4824-bfcb-5d562faec371.png">

And lastly, I worked with the last table called `vine_table` to perform the Vine program analysis to filter the best reviews, and see if there were significantly more 5-star reviews in the paid and incentivized (vine) program. The best reviews were those that were highly voted as helpful. Then, I filtered to see which of those were part of the vine program and which were not. Please refer to the [Amazon_Vine_Analysis.ipynb](https://github.com/nicoserrano/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb) 

## Results
- Paid Vine Program
  - 33 total reviews
  - 15 5-star reviews
  - ***45.5%*** of vine reviews were 5-star

- Unpaid reviews
  - 45,388 total reviews
  - 23,733 5-star reviews
  - ***52.3%*** of unpaid reviews were 5-star


## Summary

In conclusion, the vine program might just not be worth it for the apparel category. As it can be seen, there were not many helpful reviews that made part of it (total of 33), and only around half of them were 5-star rated (45%). Very similarly to the unpaid reviews which also only half of them were 5 star rated (52%). Even though the percentages may be misleading as the volume of reviews in the vine and non-vine programs vary so much, this itself is a sign that the vine program is not very popular in this category. We might not want to pay for it as it is not incentivizing the people to write better reviews. 

This allows us to conclude that customers don't feel a positivity bias for leaving good reviews in the paid program as there are so few and not so many well-rated. Nevertheless, if we were to further analyze we could calculate the mean of the star ratings on each programs' reviews to see if there's a significant incentive. 

![Screen Shot 2021-09-02 at 1 10 18 PM](https://user-images.githubusercontent.com/83378141/131887983-807ac118-b426-4db4-af18-209d85d2d80b.png)

In fact, there is a slight 0.2 difference in the average review star-rating in favor of the vine program. However, there is still not enough information to enroll in it. A great recommendation would be to apply a NLP sentiment analysis to check for the words used in the majority of the reviews. This way we could see if vine reviews are more touching and detailed, that we can feel customers have an incentive to leave great reviews.


