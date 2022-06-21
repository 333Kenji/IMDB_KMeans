# Clustering IMDB Movie Data

## Project Description

This is a clustering project where I use an enhanced KMeans model to discern clusters in a large collection of IMDB film data.


In this project I employ KMeans++ on a dataset of  Principal Component Analysis, to cluster a selection of films using data obtained from <a href="#about-the-project">IMDB</a>.

KMeans++ is simililar to KMeans in that centroid placement is random. However, unlike the 'vanilla' KMeans which randomly selects datapoints as centroids, KMeans++ only places the first centroid at random. The remaining centroids are selected based on their squared distance from those already selected.



## Major Challenges
The major challenges presented by this project are:
First, paring down and engineering the hefty IMDB data files into a dataframe of relevant features.
Second, then transforming the features so their distributions and scale allow the model to build clusters with the lowest possible spreads.
And finally, developing a the KMeans++ model with Principal Component Analysis.

## Packges & Libraries
numpy
pandas
sklearn
 - KMeans
 - PCA
 - OrdinalEncoder, OneHotEncoder
 - StandardScaler
 - ColumnTransformer
matplotlib
seaborn

## Methods Employed
- Inferential Statistics
- Machine Learning
  - KMeans
- Feature Selection
  - PCA
- Data Visualization
- Predictive Modeling


## Project Description
### 1. Data
The data for this project comes from https://www.imdb.com/interfaces/ as extremely large .tsv (tab-seperated) files, the biggest being over 2GB. In order to conduct train the KMeans++ model I will need to combine all of this data. But first, in order to load it without overloading my system I need to apply some data wranging and engineering. The need for each of these files is briefly explained below.

- akas: I need region data so I can narrow the data to 'US' based films.
- basics: contains movie specific info
- name: contains names of cast and crew along with their reference code (nconst)
- principals: contains order of precedence if more than one nconst (person) is referenced to the same role (i.e. lead vs co-directors)
- ratings: holds IMDB user rating and vote counts

I'm handling this huge memory load by using pandas to read load the data in chunk, and filtering out specific columns and values that are irrelevant to the project. The data is then saved to a .csv file to ensure stability (of my machine) that I load back in.


#### data dictionary
tconst  =   title id of the movie
primarytitle    =   common name for each film
startyear   =   release year
runtimeminutes  =   film duration
genres  =   list of each genre the film represents
ordering    =   order of precedenceif more than one individual in a givel 
category    =   job category
averagerating   =   average IMDB user rating
numvotes    =   number of IMDB votes
primaryname =   crew/castmember name

### 1.1 Loading & Wrangling
- Using Pandas I reduced five large (one is 2GB+) .tsv files downloaded from IMDB by loading in only select features and values that're relevant to this project.
- These tables are then concatenated, using Pandas, into a main dataframe that I save locally and reload in order to preserve system stability.



### 2. EDA & Feature Analysis
- Features are analyzed and trimmed using Pandas and Seaborn (for visualization).
- I primarily employ countplots, histogrames, and kde plots to visually examine each feature.
- In some cases, with numeric features, I use the interquartile range to trim off outliers.
 - Using descriptive statistics I discovered and removed outliers using the IQR method of identifying data outside 1.5 times the upper and lower IQR boundaries as statistical outliers.

### 3. Feature Selection & Hyperparameter Tuning
After checking a range of cluster quantities I use principal component analysis to to reduce the dimensionality of the data. To deal with the categorical variables I'm going to encode them ordinally so can feed the information to the KNN++ model without having to dramatically increase the feature space.


#### 3.1 Feature Selection

A key concept with PCA is that the first features considered matter the most - I'd originally struggled to get good metrics because of how I was feeding data in via the pipeline.
primaryname explodes when one hot encoded, primarytitle follows. Since I reduced genres down to a list of quintessential genres (i.e. not a list of genres. "Drama" vs "['Drama', 'Horror']").

- In order to preserve information without increasing dimesnaionality I use an ordinal encoder on the categorical features I'd like to keep for modelling.
- I use a column transformer from SKlearn to prepare the taining data that'll be used for finding the optimal number of clusters (k) and clusters (PCA).
- All numeric features, including the new ordinal features derived from himly dimensional categoricals, are passed through a standard scalar.
- One hot encoding is used for 'category' and 'genre' which both have only a handlful of features.
- Using Matplotlib, Pandas, and SKlearn I employ the elbnow method to judge the best number of clusers.
- Using on SKlearns' PCA implementation I check for the optimal number of features to abstract the base feature space into.


### 3.2 Feature Encoding
I'm using a column transformer to encode the X, which is the same as data but with a selection of categorical features ordinally encoded. It will return x_train which I'll then use for finding the optimal number of centroids (k) and components (PCA).


### 3.3 Optimal K: Elbow Method

### 3.4 Principal Component Analysis

### 3.4.1 Finding Optimal N-Components Using Optimal K
In order to find the optimal number of components to abstract the feature set into I need to analyze the entire table to find both the total variance and its 95% percentile. The number of components that can reduce variance by 5% is what we'll go with.

#### 3.4.2 Rechecking For Optimal K-Means Using Optimal N-Components
Using PCA with this optimal number of components to add a preprocessing layer to the data before applying KMeans.

### 4. Training KMeans ++ with PCA
- Using the table of PCA and the Elbow method I change/affirm the number of clusters required and train the final KMeans++ model.

### 5. KMeans++ Model and PCA Evaluation


### 6. Cluster Analysis




