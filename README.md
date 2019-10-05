## EECS 731 Project 3: Clustering by Matthew Taylor

### Overview

This project is meant to serve as an introduction to unsupervised learning. The goal is to create a movie recommendation system similar to ones used by services like Netflix. This system will rely on an unsupervised learning method called clustering.

### Approach

I began by downloading [this dataset](http://files.grouplens.org/datasets/movielens/ml-latest-small.zip), which contains information about movies. This includes titles, ratings, genres, and tags, which are keywords from reviews. Once I had the data, encoded the genres of each movie. This simply put the information in a form that will be more useful later. Then, used the many ratings for each movie to calculate a single average rating for each. Next, I grouped and encoded tags for each movie. Soon after vectorizing and clustering these tags, however, I noticed that this approach placed a majority of all movies in a single cluster. This observation caused me to persue other ideas. I went on to cluster movies using KMeans based only on ratings and genres, which gave surprising results.

### How to Run

This project was written in a Jupyter Notebook running Python 3.7.2. This project relies on a small number of modules, which can be installed by running this command:
```
pip3 install -r requirements.txt
```

Once the requirements are installed, each of the cells in the Jupyter Notebook can be executed. However, this is not required as each cell has already been executed and the results are shown.

### Results

Because our data is unlabeled, the accuracy of the resulting model must be determined manually. To accomplish this, I wrote a function that took the title of a movie as an input. This function utilized the clustering model I trained to return related movies based on genre and rating. I decided to test it with two very different inputs, Toy Story and John Wick. Sure enough, all of the Toy Story recommendations were animated children's movies, while all of the John Wick recommendations were high-octane thrillers.
