# Analyzing 10Gb of Yelp Reviews Data

I analyzed a subset of Yelp's business, reviews and user data. This dataset comes to us from [Kaggle](https://www.kaggle.com/yelp-dataset/yelp-dataset) 
1. I created EMR Cluster and created a notebook.
2. I downloaded the dataset from [Kaggle](https://www.kaggle.com/yelp-dataset/yelp-dataset). 
3. I created a s3 bucket and pull this dataset into it.s3://project02-jason/yelp_academic_dataset_business.json, 's3://project02-jason/yelp_academic_dataset_review.json','s3://project02-jason/yelp_academic_dataset_user.json'


## Analysis 

Part I: Installation and Initial Setup

I installed necessary packages such as Pandas, Seaborn and matplotlib. I also imported them as needed. 


Part II: Analyzing Categories

I applied my python knowledge to all the questions as needed. Select required columns from original dataset and join them into one dataset for better analysis.


Part III: Do Yelp Reviews Skew Negative?

I added an addition column(skew=(row['avg(stars)'] - row['stars']) / row['stars']） to figure out if review writer rating business differently because people are likely to write negative review when they had poor experience with the business. The result is very obvious. Based on my analysism review writers rated business lower than the actual rating.

Extra work
1. I counted the total number of negative skews and postive skews to prove if my assumption is right. The result is count(negative skew)>count(positive skew).
2. I also groupby the dataset by business categroies to see which categories are affected the most.


Part IV: Should the Elite be Trusted?

I filtered out all the elite members and summarized they average rating scores to different business. Compare with the random review writers' rating scores from last question, I ended up getting the elites' ratings that are really closed to the actual business ratings. So I think they are trust worthy.

## Cluster and Notebook Configs

![notebook](https://github.com/mottaquikarim/STA9760_Project2_Yelp_Data_Analysis/blob/master/assets/notebook.png?raw=true)
![cluster](https://github.com/mottaquikarim/STA9760_Project2_Yelp_Data_Analysis/blob/master/assets/cluster.png?raw=true)
