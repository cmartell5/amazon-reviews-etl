# Big-Data-ETL

## Background
For this project I will put my ETL skills to the test. Many of Amazon's shoppers depend on product reviews to make a purchase. Amazon makes these datasets publicly available. They are quite large and can exceed the capacity of local machines. One dataset alone contains over 1.5 million rows; with over 40 datasets, data analysis can be very demanding on the average local computer. My first goal will be to perform the ETL process completely in the cloud and upload a DataFrame to an RDS instance. The second goal will be to use PySpark or SQL to perform a statistical analysis of selected data.

* Part 1: Extract two Amazon customer review datasets, transform each dataset into four DataFrames, and load the DataFrames into an RDS instance.
    
## Project Steps
1. Extracted data - Two Amazon customer review datasets into Spark DataFrames. One was for video games and one was for pet products.
    * https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz 
    * https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Pet_Products_v1_00.tsv.gz
2. Transformed data - Created four dataframes from each dataset based off the information extracted:
    * "review_id_df" DataFrame with appropriate columns and datatypes
    * "products_df" DataFrame that drops the duplicates on the "product_id" and "product_title" columns
    * "customers_df" DataFrame that groups the data on the "customer_id" by the number of times a customer reviewed a product
    * "vine_df" DataFrame that has the "review_id", "star_rating", "helpful_votes", "total_votes", and "vine" columns
3. Load data - Exported each DataFrame into the RDS instance to create four tables for each dataset

## Tools used: 
Google Colab, AWS, Spark, postgresql, java, hadoop
