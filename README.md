# css4p01.py
CSS Project - Option 1: IMDB Data
# -*- coding: utf-8 -*-
"""
Created on Sat Feb  3 13:22:40 2024

@author: nosih
"""

import pandas as pd

# Load the dataset
df = pd.read_csv("movie_dataset.csv")


x = df["Revenue (Millions)"] .mean() 
df["Revenue (Millions)"]. fillna(x, inplace = True)

y = df["Metascore"] .mean()
df["Metascore"]. fillna(y, inplace = True)
print(df)


#Question 1

# Find the highest rated movie
highest_rated_movie = df[df["Rating"] == df["Rating"].max()]

# Print the details of the highest rated movie
print(highest_rated_movie)

#Question 2

# Calculate the average revenue
average_revenue = df["Revenue (Millions)"].mean()

# Print the average revenue
print("The average revenue of all movies is:", average_revenue)


#Question 3

# Filter the DataFrame for movies released between 2015 and 2017 and calculate the average revenue
df= df[df["Year"]>=2015]

average_revenue = df["Revenue (Millions)"].mean()

# Print the average revenue of movies from 2015 to 2017
print("The average revenue of of movies from 2015 to 2017 is:", average_revenue)


#Question 4

df= df[df["Year"]>=2016]

print("The number of movies were released in the year 2016", df)


#Question 5

# Filter the DataFrame for movies directed by Christopher Nolan
nolan_movies = df[df['Director'].str.contains('Nolan', case=False, na=False)]


# Print the movies directed by Christopher Nolan
print("Movies Directed by Christopher Nolan:", nolan_movies['Title'].tolist())

#question 6

# Count the number of movies with a rating of at least 8.0
highly_rated_movies = df[df['Rating'] >= 8.0].shape[0]

# Print the number of movies with a rating of at least 8.0
print("The number of movies with a rating of at least 8.0 is:", highly_rated_movies)

#Question 7

# Calculate the median rating of Christopher Nolan's movies
median_rating_christopher_movies = christopher_movies_movies['Rating'].median()

print("Median Rating of Christopher Nolan's Movies is:", median_rating_cchristopher_movies)

#Question 8

df=df[df["Year"]==2006]
dfdf=df.mean ()
print(dfdf)

#9
movies_2006 = df[df['Year'] == 2006]
movies_2016 = df[df['Year'] == 2016]

# Calculate the number of movies made in 2006 and 2016
number_movies_2006 = len(movies_2006)
number_movies_2016 = len(movies_2016)


percentage_increase = ((number_movies_2016 - number_movies_2006) / number_movies_2006) * 100


print("The percentage increase in the number of movies made between 2006 and 2016 is:", percentage_increase, "%")



#10

actors = df['Actors'].str.split(',').explode().str.strip()
actor_counts = actors.value_counts ()
most_common_actor = actor_counts.idxmax()
print("The most common actor in all the movies is:",most_common_actor)

#11
genres = df['Genre'].str.split(',').explode().str.strip()

unique_genres_count = genres.nunique()

print("The number of unique genres in the dataset is:", unique_genres_count)




















