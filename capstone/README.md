# Capstone Project: Auto-categorising Mobile Product Information with Free Texts and Images

## Executive Summary 

In 2017, Global e-commerce transactions generated $29.267 trillion, including $25.516 trillion for business-to-business transtions and #3.851 trillion for business-to-consumer sales. With advancements in technology, businesses have invested in building mobile applications to get closer with their customers and we see more tradtional businesses moving towards e-business. Borders are torn down as businesses can reach out to customers globally. 

## Problem Statement 

With large amounts of free text and images being uploaded to e-commerce platforms for businesses and users to sell their products, we need a better way to categorise the products to ensure our users reach their target audiences. I have built an auto-categoriser for mobile product information, extracting product information from free texts and images. 

I will be using the mobile data sets from the National Data Science Challenge 2019 by Shopee for my data science problem. 

## Overview

There are 4 notebooks to my auto-categoriser:

* Attribute Decoder 
* Mobile Data Exploratory Data Analysis
* Mobile Brand
* Mobile Colour 

I will be working on individual columns (Brand and Colour) separately as the number of missing data defers for each column. 

### Data Source

[Shopee: National Data Science Challenge 2019](https://www.kaggle.com/c/ndsc-advanced/data)

## Data Analysis

### Brand

There are 55 unique brands for mobile products on Shopee. Samsung holding the greatest market share at 22.1% and Apple coming in next at 20.3%. 

I also noticed that there are many non-english (Bahasa) terms used in the free text. This might be due to the popularity of Shopee in Malaysia and Indonesia. It was even found to be the preferred app for Indonesian mothers.

[Source](https://www.marketing-interactive.com/shopee-found-to-be-the-most-popular-e-commerce-site-for-indonesian-mothers)

### Colour

There are 26 unique colours for mobile products on Shopee. The colour with the greatest market share is Black at 44.0% followed by Gold at 20.2%. 

The images uploaded by users can be categorised into the following:

* Image of the phone
* Image of the phone with the packaging 
* Image of the packaging
* Image of multiple phones
* Advertisement for the phone 

## Feature Engineering & Preprocessing

### Brand

I classified the small brands with little market share under 'Others' reducing it to classification problem of 20 classes. I used the Tfidf Vectorizer here to vectorise the free texts for the mahcine to process. 

Tf stands for 'term frequency' while idf stands for inverse document-frequency.    It evaluates how important each term is to a document and it is then offset by the frequency of the term. It penalises common words and give rare words more influence. 

### Colour

Similar to Brand, I classfied the rarer colours as 'Others' reducing it to a images classification problem of 8 classes. I first changed each image to an array and then reshaped to dimensions of 224 x 224 x 3. I will be making use of the highly successfull VGG16 model and a technique called transfer learning.

VGG16 is a convultional neural network model from the University of Oxford which has achieved 92.7% accuracy for a dataset with 14 million images belonging to 1000 classes. I picked this model as it is accurate, readily available and comes with pre-trained weights. 

Transfer learning refers to a method of applying stored knowledge gained while solving one problem to another related problem. In our case, the stored knowlegde refers to the pre-trained weights that come with the VGG16 model. 

## Modelling

### Brand

I used Logistic Regression and obtained an accuracy of 98.56% on unseen data. I then looked at the misclassified devices to see if I could improve the model further. I extracted the top 25 words from the misclassified devices and created a custom list of stopwords. I ran the Logistic Regression model again, this time with my custome list of stop words, and managed to obtain a slight improvement of 98.58% accuracy on unseen data. 

### Colour

I first removed the last 3 layers of the VGG16 model, loaded the pre-trained weights and froze the training layers. Then, I added 2 of my own layers so that the model gives an output of 8 classes. I ran the model with 20,000 images for 10 epochs and obtained an accuracy of about 50.3%. 

## Conculsions and Findings

### Brand

The attempt to tune the model was successful as it is likely that the top 25 words in the misclassified devices were common across many of the devices. e.g. 32 gb, wifi

The reason for not including brand names or model names in stop words is because some models are exclusive to certain brands. e.g iPhone for apple or S8 for Samsung. These words actually help to better separate phone brands further, which has likely contributed to the high accuracy of the model. 

As there are many non-english terms in this model, we could employ a language domain expert to pick up those words to be included in our custom list of stop words to further improve the model. 

### Colour

There were many phones which are White but were predicated as Gold likely because of the packaging of the devices. e.g. Apple rose gold. There are also more than twice as many gold phones compared to white phones in the training data (17162 vs 7883). As such, when presented with a white phone, the model is more likely to predict a white phone as gold. 

I also used the base VGG16 model to check the mobile images. 'cellular_telephone' (Synset: cellular telephone, cellular phone, cellphone, cell, mobile phone) did not show up as the top result for most of them despite them all being mobile images. This suggests that the images uploaded could have been better without their packaging or other obstructions. 

### For the model to be successful...

I believe some guidelines need to be set for customers to follow when posting products. They should post in English and post images with less noise. There will also be a need for human resource integration. As in both models, the smaller brands and rarer colours have been clustered under 'Others'. We will need a human resource to accurately label the devices that get sorted into 'Others'. 

















