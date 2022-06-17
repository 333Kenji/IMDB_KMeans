??? Banner


# KMeans IMDB Clustering

This project is an exploration of the KMeans clustering process using IMDB movie data.

??? data.head() img

## Authors

- Kenji Alford [GIT](https://www.github.com/333kenji)

??? Embiggen (or not)
<!-- TABLE OF CONTENTS -->
<details>
    
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>


---
??? Linky
The notebook(s) for this project can be found here.


## Motivations

Project introduction.

I'm doing this project to build intuition in clustering using the KMeans algorithm. The project goal is to successfully develop clusters of movies while also producing their profiles, i.e. the typical values associated with each. The major challenges presented by this project are first, paring down the hefty IMDB data files into a data frame of relevant features, then transforming the features so their scale and centering permit an acceptable estimation grouping before modeling.
- By transforming the data and selecting the optimal number of centroids I'm able to develop a KMeans model.
- Evaluation Metrics.
    - model accruacy and the elbbow method.
- Minimum viable product.
    - A model that can both accurately group and also describe clusters within the data.


---
## Methodologies
### Methods Employed
- Inferential Statistics
- Machine Learning
    - Why this algorithm
- Data Visualization
- Predictive Modeling
- etc.
## Libraries and Technologies
- Python
- Numpy, Pandas
- Scikit-learn
- Jupyter, VSCde

---
## Project Description
### Technical Aspect
1. Data
- Using Pandas I reduced five large (one is 2GB+) .tsv files downloaded from IMDB by loading in only select features and values that're relevant to this project.
- These tables are then concatenated, using Pandas, into a main dataframe that I save locally and reload in order to preserve system stability.

2. EDA
- Features are analyzed and trimmed using Pandas and Seaborn (for visualization).
- I primarily employ countplots, histogrames, and kde plots to visually examine each feature.
- In some cases, with numeric features, I use the interquartile range to trim off outliers.

3. Feature Selection & Hyperparameter Tuning
- In order to presefve information without increasing dimesnaionality I use an ordinal encoder on the categorical features I'd like to keep for modelling.
- I use a column transformer from SKlearn to prepare the taining data that'll be used for finding the optimal number of clusters (k) and clusters (PCA).
- All numeric features, including the new ordinal features derived from himly dimensional categoricals, are passed through a standard scalar.
- One hot encoding is used for 'category' and 'genre' which both have only a handlful of features.
- Using Matplotlib, Pandas, and SKlearn I employ the elbnow method to judge the best number of clusers.
- Using on SKlearns' PCA implementation I check for the optimal number of features to abstract the base feature space into.

4. Training KMeans ++ with PCA
- Using the table of PCA and the Elbow method I change/affirm the number of clusters required and train the final KMeans++ model.




This project relies heavily on visual analysis
1. Loading Data

2. EDA
    - Through an EDA of descriptive statistics I discovered, and removed outliers using the IQR method of removing data outside 1.5 times the upper and lower IQR boundaries..
3. Preprocessing
    - 
 ### Experimental Design
 - target
 - the control/test split
 - the validation set
 - ML algorithm stack
 ### The Data

Description of Data Acquisition
Date of collection
Description of each data source
- Source
How Sources May Be Related
Variables Directory
- column headings
- types
- number of variables
- units of measurement
- Definition of missing data
Directory Tree
Description of Methods of Data Processing
- Wrangling
- Transformation
- Encoding
- Scaling

---
## Summary
### Noteworthy Findings w/Graphics
- this
- that
- and another thing


Information About Model
Model Evaluation
    - [Model Card](https://arxiv.org/pdf/1810.03993.pdf)
Predictions
Real World Applications

---
<!-- ROADMAP -->
## Roadmap

- [x] Add Changelog
- [x] Add back to top links
- [ ] Add Additional Templates w/ Examples
- [ ] Add "components" document to easily copy & paste sections of the readme
- [ ] Multi-language Support
    - [ ] Chinese
    - [ ] Spanish