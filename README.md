# Movie Recommender System

## Introduction

In this project, we will be building a movie recommendation system using two different techniques: content-based filtering and collaborative-based filtering. The goal is to provide personalized movie recommendations to users based on their tastes and preferences.

To build the recommender system, we will be using a dataset from [MovieLens](http://movielens.org), a movie recommendation service. The dataset contains ratings data for over 34,000 movies, provided by over 247,000 users between January 1995 and January 2016. The dataset includes information about the movies (e.g. title, genres) and the ratings provided by users (e.g. userId, movieId, rating, timestamp).

The data are contained in four files, `links.csv`, `movies.csv`, `ratings.csv` and `tags.csv`. However for this project, we will be using only 'movies.csv' and 'ratings.csv'.

Movies.csv - movieId, title and genres. It consists of 34,208 movies.
Ratings.csv - userId, movieId, rating and timestamp - It consists of total of 22884377 ratings.

Check out other datasets at https://grouplens.org/datasets/movielens/. To understand more about dataset, read the Dataset-info.txt. 

Once we have built the recommendation models, we will deploy them on Amazon Web Services (AWS) using the Flask web framework, making them easily accessible to users through a web interface.

## Recommender Model

### Content-Based Recommender Model

A content-based recommender system works by creating a user profile based on the ratings a user has provided for different movies. It then recommends movies to the user based on the similarity of the items to the user's profile. For example, if a user rates highly for movies in the action genre, the user's profile will have a high weight for that genre, and the recommendation system will suggest new action movies to the user. The recommendation process is based entirely on the user's tastes and preferences.

To build the content-based recommendation model, we will follow these steps:

* Preprocess the dataset by handling missing values and performing data transformations.
* Generate a list of genres to simplify the recommendation process.
* Create a one-hot encoding matrix based on the different genres for each movie.
* Build a user profile based on the user's ratings.
* Recommend the top 5 movies with the highest scores.

Check out the <b>Content Based Recommendation System.ipynb.</b>

### Collaborative-Based Recommender Model

A collaborative-based recommendation system takes into account the preferences and opinions of other users in order to make recommendations. It attempts to find users with similar preferences and opinions as the input user, and then recommends items that they have liked. For example, if a user gives a high rating to a particular movie, the recommendation system will find other users with similar opinions and suggest movies based on their interests.

To build the collaborative-based recommendation model, we will follow these steps:

* Preprocess the dataset by handling missing values and performing data transformations.
* Select a user and the movies they have watched.
* Find the top 100 nearest neighbors based on the user's ratings.
* Get the watched movie records for each neighbor.
* Calculate a similarity score using a chosen formula.
* Recommend the top 5 items with the highest scores.

Check out the <b>Collaborative Based Filtering System.ipynb.</b>

## Deployment

Your end users don't want to see your Jupyter Notebooks. You need to have a way to deploy your models using a web framework so it makes them easy to use and accessible from anywhere. For this project, the content based recommender model has been <b> deployed on AWS using Flask web framework. </b>

Flask Web Framework - It is one of the best web framework to deploy your models as it has variety of choices for developing applications and support of tools and libraries.

To run the Flask application, add the dataset files to the FLASK folder. On the terminal, type python app.py. It will take few seconds to launch. Once it indicates that it is running, enter localhost:8080 in web browser.

![alt text](https://github.com/adiark/Movie-Recommendation/blob/main/FLASK/app_images/Picture_1.png)

![alt text](https://github.com/adiark/Movie-Recommendation/blob/main/FLASK/app_images/Picture_2.png)
