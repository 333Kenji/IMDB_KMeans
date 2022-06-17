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
I'm doing this project to build intuition in clustering using the KMeans algorithm.
The project goal is to succesfully develop clusters of movies while also producing their profiles, i.e. the typical values associated with each.
The major challenges presented by ths project are first, paring down the hefty IMDB databse files into a dataframe of relevant features, then transforming the features so their scale and centering permits an accepable estimation grouping prior to modeling.
The Solution
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
2. Initial EDA
- 
    2.1 Data Diagnosis
    
    2.2 Categorical Features
    
    2.3 Numeric Features
    
    2.4 Feature Associations
    
3. Feature Selection & Hyperparameter Tuning
    
    3.1 Feature Selection
    
    3.2 Feature Encoding
    
    3.3 Optimal K: Elbow Method
    
    3.4 PCA
    
    3.4.1 Finding Optimal N-Components Using Optimal K
    
    3.4.2 Rechecking Optimal K Using Optimal N-Components
    
4. Training KMeans ++ with PCA
5. KMeans++ Model and PCA Evaluation
6. Cluster Analysis



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