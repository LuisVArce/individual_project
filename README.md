# <a name="top"></a>Beer Analysis: Can we predict a good beer?
![]()

by: Luis Arce



***
## Executive Summary

[[Project Description](#project_description)]

With more breweries than ever in America, it is more important than ever to have your product standout. I’ve been provided a dataset with 12 continuous and categorical features. The features supplied are descriptive features of beers provided by beer reviewers. I will analyze this dataset to see if we can provide a beer producer with attributes that they should focus on in order to receive a high overall beer score. Beer production is both a science and an artform and a beers final attribute can be manipulated in many ways.

[[Project Planning](#planning)]

I will be trying to predict a continuous variable, so I will employ a regression model in order to predict my target variable. 

My goal is to predict my y variable, review_overall. I will consider my models a success if I can beat the average score of my current beer values with a lower root mean square error as a metric of success. I will follower the data science pipeline of Acquisition, Preparation, Exploration and Modeling. 

[[Key Findings](#findings)]

My original hypothesis was that beer_abv (abv = alcohol by volume. Basically, how much booze is in a drink) would have an affect on a beer’s review_overall. It turns out that it has little to no connection to a final beer’s score. 

In order -  taste, palate, aroma and appearance all have an influence on a beer’s overall review score.

[[Data Dictionary](#dictionary)]


0   brewery_id       =  Unique brewery ID = int64  
 1   brewery_name    =    Name  = object 
 2   review_time      =   How long it took to review  = int64  
 3   review_overall    =  review attribute =  float64
 4   review_aroma      =  review attribute  = float64
 5   review_appearance =  review attribute = float64
 6   review_profilename =  review attribute = object 
 7   beer_style         = type of beer = object 
 8   review_palate    =   review attribute = float64
 9   review_taste       = review attribute = float64
 10  beer_name         =  self explantory = object 
 11  beer_abv          =  alcohol by volume = float64
 12  beer_beerid       =  unqiue beer id = int64


[[Data Acquire and Prep](#wrangle)]

I’ve acquired the dataset from data.world. I’ve read it into my local csv from the website. The preparation section was fairly easy. I scrubbed for outliers, filled in null values with zero’s where applicable. The missing values for abv was determined by the mean average for the beers in the column. I also dropped useless columns.

[[Data Exploration](#explore)]

I used pairplots and various visualizations in order to draw some conclusions. 

[[Statistical Analysis](#stats)]

I used T-tests, correlation tests and asked questions of the data.

[[Modeling](#model)]
The baseline is the average of the review_overall. My model methods are OLS, Tweedie etc.

[[Conclusion](#conclusion)]

Beer’s overall high score is determined by the beer’s taste, palate, aroma and appearance. Beer abv has little to do with a positive review. If there was more time, I would perform a clustering model to see if we can predict a beers missing abv by its beer type. Also, it would be useful to have a brewery ID key in order to determine where the beers are from. Sales data would help to determine what styles of beers sell more and where they sell more. 

My recommendation is to focus on the taste of a beer with paying special attention to its aroma as well. Beer abv is of little relevance to a beers actual taste and should be disregarded for the most part. 
___

<img src="https://docs.google.com/drawings/d/e/2PACX-1vR19fsVfxHvzjrp0kSMlzHlmyU0oeTTAcnTUT9dNe4wAEXv_2WJNViUa9qzjkvcpvkFeUCyatccINde/pub?w=1389&amp;h=410">

## <a name="project_description"></a>Project Description:
[[Back to top](#top)]

***
## <a name="planning"></a>Project Planning: 
[[Back to top](#top)]

### Project Outline:

Data science pipeline
        
### Hypothesis

Beer_abv is related to a beer’s overall review score.

### Target variable

Y = Review_overall

### Need to haves (Deliverables):

Final notebook and README

### Nice to haves (With more time):

-	Brewery ID key
-	Location of breweries
-	IBU – bitterness of beer



***

## <a name="findings"></a>Key Findings:
[[Back to top](#top)]

My original hypothesis was that beer_abv (abv = alcohol by volume. Basically, how much booze is in a drink) would have an affect on a beer’s review_overall. It turns out that it has little to no connection to a final beer’s score.

In order - taste, palate, aroma and appearance all have an influence on a beer’s overall review score.


***

## <a name="dictionary"></a>Data Dictionary  
[[Back to top](#top)]

### Data Used
---
| Attribute | Definition | Data Type |
 0   brewery_id          Unique brewery ID int64  
 1   brewery_name        Name  object 
 2   review_time         How long it took to review  int64  
 3   review_overall      review attribute  float64
 4   review_aroma        review attribute  float64
 5   review_appearance   review attribute  float64
 6   review_profilename  review attribute  object 
 7   beer_style          type of beer  object 
 8   review_palate       review attribute  float64
 9   review_taste        review attribute  float64
 10  beer_name           self explantory  object 
 11  beer_abv            alcohol by volume  float64
 12  beer_beerid         unqiue beer id  int64 

***

## <a name="wrangle"></a>Data Acquisition and Preparation
[[Back to top](#top)]

![]()


### Wrangle steps: 


*********************

## <a name="explore"></a>Data Exploration:
[[Back to top](#top)]
- Python files used for exploration:
    - wrangle.py 
    - explore.py
    - modeling.py


### Takeaways from exploration:


***

## <a name="stats"></a>Statistical Analysis
[[Back to top](#top)]

### Stats Test 1: ANOVA Test: One Way

Analysis of variance, or ANOVA, is a statistical method that separates observed variance data into different components to use for additional tests. 

A one-way ANOVA is used for three or more groups of data, to gain information about the relationship between the dependent and independent variables: in this case our clusters vs. the log_error, respectively.

To run the ANOVA test in Python use the following import: \
<span style="color:green">from</span> scipy.stats <span style="color:green">import</span> f_oneway

- f_oneway, in this case, takes in the individual clusters and returns the f-statistic, f, and the p_value, p:
    - the f-statistic is simply a ratio of two variances. 
    - The p_vlaue is the probability of obtaining test results at least as extreme as the results actually observed, under the assumption that the null hypothesis is correct

#### Hypothesis:
- Null Hypothesis: review_taste is independent of review_overall.
- Alternate Hypothesis: review_taste is correlated with review_overall.

- Null Hypothesis = There is no relationship between beer_abv and review_overall
- Alternative Hypothesis = There is a relationship with beer_abv and review_overall

- Null Hypothesis: The mean of review_taste is equal to review_palate.
- Alternate Hypothesis: The mean of review_taste is significantly different than review_palate.


#### Confidence level and alpha value:
- I established a 95% confidence level
- alpha = 1 - confidence, therefore alpha is 0.05
- I also ran a 99% confidence interval for one stat test.

#### Results:


#### Summary:


### Statistical test used:
- Pearson's Correlation
- Spearmans Correlation
- Two-Tailed T-test


#### Confidence level and alpha value:
- I established a 95% confidence level and in one stats test, a 99$ confidence level.
- alpha = 1 - confidence, therefore alpha is 0.05


#### Results:


#### Summary:

### To Reconstruct this Project
You'll require own env.py file to store query connection credentials(access rights to CodeUp SQL is required).
Read this ReadMe.md file fully and make necessary files
Set up .gitignore file and ignore env.py, *.csv files
Create and Repository directory on GitHub.com
Follow instructions above and run the final zillow_workspace report.

***

## <a name="model"></a>Modeling:
[[Back to top](#top)]

### Model Preparation:

### Baseline
    
- Baseline Results: 3.815
- Baseline RMSE using mean: .71
- Baseline RMSE usine median: .73
    

- Selected features to input into models:
    - features = [brewery_id', 'brewery_name', 'review_overall', 'review_aroma',
       'review_appearance', 'beer_style', 'review_palate', 'review_taste',
       'beer_name', 'beer_abv']

***

### Models and R<sup>2</sup> Values:
- Will run the following regression models:
- OLS Regression
- Lasso + Lars
- GLM using Tweedie

    

- Other indicators of model performance with breif defiition and why it's important:

    
    
#### Model 1: Linear Regression (OLS)


- Model 1 results:
RMSE for OLS using LinearRegression

- Training/In-Sample: 0
- Validation/Out-of-Sample: 0.409688650223883


### Model 2 : Lasso Lars Model


- Model 2 results:
RMSE for Lasso + Lars

- Training/In-Sample: 0.5838810630246742
- Validation/Out-of-Sample: 0.7131881375527451

### Model 3 : Tweedie Regressor (GLM)

- Model 3 results:
RMSE for GLM using Tweedie, power=1 & alpha=0

- Training/In-Sample: 0.07554060365014124
- Validation/Out-of-Sample: 0.4236598025095658


- {} model performed the best
GLM with Tweedie

## Testing the Model

- Model Testing Results
- RMSE for OLS Model using LinearRegression
- Out-of-Sample Performance:  0.42258894982438566
***

## <a name="conclusion"></a>Conclusion:
[[Back to top](#top)]
Beer’s overall high score is determined by the beer’s taste, palate, aroma and appearance. Beer abv has little to do with a positive review. If there was more time, I would perform a clustering model to see if we can predict a beers missing abv by its beer type. Also, it would be useful to have a brewery ID key in order to determine where the beers are from. Sales data would help to determine what styles of beers sell more and where they sell more.

My recommendation is to focus on the taste of a beer with paying special attention to its aroma as well. Beer abv is of little relevance to a beers actual taste and should be disregarded for the most part.

