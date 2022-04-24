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

<img width="745" alt="Screen Shot 1" src="https://github.com/dannybarto/Amazon_Vine_Analysis/blob/d04215bcca511501928c6c3d3d71f3c6329ac449/Resources/131558905-90cc438b-fd27-476c-808f-95096f8b9dcb.png">
<img width="743" alt="Screen Shot 2" src="https://github.com/dannybarto/Amazon_Vine_Analysis/blob/d04215bcca511501928c6c3d3d71f3c6329ac449/Resources/131558907-b7ba32fc-1752-4fcb-8d4f-9da12cac9ceb.png">
<img width="740" alt="Screen Shot3" src="https://github.com/dannybarto/Amazon_Vine_Analysis/blob/d04215bcca511501928c6c3d3d71f3c6329ac449/Resources/131558908-a2c084ee-6702-42b7-9355-22e2bab1c772.png">
<img width="741" alt="Screen Shot 4
" src="https://github.com/dannybarto/Amazon_Vine_Analysis/blob/d04215bcca511501928c6c3d3d71f3c6329ac449/Resources/131558909-3b5a6ef3-c351-4824-bfcb-5d562faec371.png">

 `Vine_Review_Analysis` was used to perform the Vine program analysis to filter the best reviews, and see if there were significantly more 5-star reviews in the paid and incentivized (vine) program. The best reviews were those that were highly voted as helpful. Then, I filtered to see which of those were part of the vine program and which were not. 

## Results
- Paid Vine Program
  - 1,080 total reviews
  - 454 5-star reviews
  - ***42.03%%*** of vine reviews were 5-star

- Unpaid reviews
  - 49,673 total reviews
  - 23,043 5-star reviews
  - ***46.38%*** of unpaid reviews were 5-star


## Summary

Based on the analysis above the Vine program does not appear to provide any benefit over the unpaid reviews for the electronics category. It doesn't appear that there is any bias on the part of users who participate in the Vine program

While not statistically significant it actually appears that the potential seller would be better off not enrolling in the Vine program at all.


