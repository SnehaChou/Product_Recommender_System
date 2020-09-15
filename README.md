Developed a Product Recommendation System and compared the different techniques available for building a Recommendation System.

## Dataset Description
The dataset has been collected from Kaggle competition (https://www.kaggle.com/olistbr/brazilian-ecommerce)
The dataset has information of 100k orders from 2016 to 2018 made at multiple marketplaces in Brazil. Its features allows viewing an order from multiple dimensions: from order status, price, payment and freight performance to customer location, product attributes and finally reviews written by customers. We also released a geolocation dataset that relates Brazilian zip codes to lat/lng coordinates.
Customers - 99k
Orders - 100k
Products - 32k

Use the zip folder to extract the dataset.

<img src="Images/dataset.png" width=500>

## Content based Filtering

Product recommendation is done based on Content similarity between products.
Similarity is calculated using cosine similarity.

A major drawback of this algorithm is that it is limited to recommending items that are of the same type. It will never recommend products which the user has not bought or liked in the past. So if a user has watched or liked only action movies in the past, the system will recommend only action movies. It’s a very narrow way of building an engine.

To improve on this type of system, we need an algorithm that can recommend items not just based on the content, but the behavior of users as well

## Collaborative Filtering

1. Non Paramateric Approach

  K- Means

2. Parametric ML Approach
Responsiveness for recommender systems translates to being able to react in almost real time to the arrival of new ratings in the system. Most recommendation algorithms need to retrain their complete model to integrate new data which can often not be done in real time. For some specific recommendation algorithms, online updating approaches have been developed such as SVD

SVD - compresses the large but sparse user-item matrix

Matrix Factorization - breaking down a large matrix into a product of smaller ones This saves both time and space

## Hybrid Filtering

A system that combines content-based filtering and collaborative filtering could potentially take advantage from both the representation of the content as well as the similarities among users.

Solves the problem of Cold Start by taking meta data into account when user-item interaction is not available.

When you deploy a collaborative model to production, you’ll often run into the problem that you need to predict for unseen users or items – like when a new user registers or visits your website, or your content team publishes a new article.

Usually you have to wait at least until the next training cycle, or until the user interacts with some item, to be able to make recommendations for these users.

But the hybrid model can make predictions even in this case: It will simply use the partially available features to compute the recommendations.

## Light FM library in Python was used to design the hybrid Recommendation System (https://www.kaggle.com/niyamatalmass/lightfm-hybrid-recommendation-system#LightFm-hybrid-recommender-for-CareerVillage)
## Model Performance with only Product Features
Accuracy - 93.12% 
## Model Performance with only Interaction Matrix
Accuracy - 97.7%
## Model Performance with both Product & Interaction Matrix
Accuracy - 94.23%
