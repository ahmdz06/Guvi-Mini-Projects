# 🏏 IPL Cricket Analysis and Winner Prediction System

## Project Overview

This project focuses on analyzing historical Indian Premier League (IPL) data and developing a Machine Learning model to predict the probable winner of an IPL match.

The project involves extensive Exploratory Data Analysis (EDA) to study team performances, player performances, toss impacts, seasonal trends, and various match statistics. Multiple Machine Learning algorithms were implemented and compared to identify the most suitable model for predicting match outcomes.

The complete project workflow includes data preprocessing, data cleaning, exploratory analysis, feature engineering, model building, model evaluation, and prediction system development.

The primary goal of this project is to demonstrate the practical application of Data Science and Machine Learning techniques in the domain of sports analytics.

# Project Details

Develop and submit an IPL Cricket Analysis and Prediction System using Data Science techniques. The project should include detailed data preprocessing, exploratory data analysis, visualization, and predictive modeling to uncover meaningful insights from historical IPL data.

The system should analyze team and player performances, seasonal trends, toss impacts, match outcomes, and various cricket statistics. In addition, the project should implement Machine Learning models to predict the probable winner of an IPL match based on historical match information.

The project should demonstrate the complete Data Science workflow, including:

* Data collection and understanding.
* Data cleaning and preprocessing.
* Handling missing and inconsistent values.
* Exploratory Data Analysis (EDA).
* Feature engineering and data preparation.
* Machine Learning model development and evaluation.
* Match winner prediction using historical IPL data.
* Presentation of analytical insights through effective visualizations.

The final submission should include a well-documented Python codebase, detailed analytical findings, and a prediction system capable of forecasting IPL match outcomes.

## Dataset Description

Two datasets were used for this project.

## 1. Matches Dataset

The matches dataset contains match-level information.

Important attributes include:

Season
City
Team 1
Team 2
Toss Winner
Toss Decision
Match Winner
Player of the Match
Venue
Umpire Details

This dataset was mainly used for:

Team analysis
Toss analysis
Seasonal analysis
Machine Learning model development

## 2. Deliveries Dataset

The deliveries dataset contains ball-by-ball information for every IPL match.

Important attributes include:

Match ID
Innings
Batting Team
Bowling Team
Batsman
Bowler
Runs scored on each delivery
Extras
Dismissal details

This dataset was used for:

Batsman analysis
Bowler analysis
Strike rate analysis
Boundary analysis
Orange Cap analysis
Purple Cap analysis
Technologies and Libraries Used

The following Python libraries were used during the development of this project.

## Library	Purpose

Pandas	Data manipulation and preprocessing
NumPy	Numerical operations
Matplotlib	Data visualization
Seaborn	Statistical visualization
Plotly	Interactive visualizations
Scikit-learn	Machine Learning model building
Project Workflow

The entire project was carried out in multiple stages.

## Stage 1: Data Collection and Loading

Initially, the IPL datasets were imported into the Jupyter Notebook environment using Pandas.

The datasets were loaded as DataFrames to facilitate analysis and preprocessing.

matches = pd.read_csv('matches.csv')
deliveries = pd.read_csv('deliveries.csv')

After loading, the structure of the datasets was explored using:

.shape
.head()
.columns
.info()

This helped in understanding the dimensions, attributes, and datatypes present in the datasets.

## Stage 2: Data Cleaning and Preprocessing

Data cleaning is one of the most important stages in any Data Science project.

The following preprocessing operations were performed:

Missing Value Handling

Missing values were identified using:

isnull().sum()

Rows with missing winner information were removed because Machine Learning models require complete output labels for training.

Missing umpire details were handled appropriately to maintain data consistency.

Duplicate Removal

Duplicate records were checked using:

duplicated().sum()

Any duplicate entries found were removed to avoid biased analysis.

## Stage 3: Exploratory Data Analysis (EDA)

Exploratory Data Analysis was performed to understand the underlying patterns present in the IPL dataset.

Several visualizations were created using Matplotlib, Seaborn, and Plotly.

## Seasonal Analysis

The number of matches played in each IPL season was analyzed.

Purpose:

To understand how the tournament expanded over time.
To identify seasons with the highest number of matches.

## Team Performance Analysis

The overall performance of IPL teams was analyzed by calculating the total number of matches won by each team.

Purpose:

To identify the most successful IPL franchises.
To compare team performances historically.
Toss Decision Analysis

Teams generally choose either batting or fielding after winning the toss.

This analysis was performed to determine:

Which decision is preferred more frequently.
Whether toss decisions significantly affect match outcomes.

## Toss Winner vs Match Winner Analysis

A new feature was created to determine whether the team winning the toss also won the match.

Purpose:

To evaluate the actual influence of toss results on match outcomes.

## Top Batsmen Analysis

Using the deliveries dataset, total runs scored by each batsman were calculated.

Purpose:

To identify the highest run scorers in IPL history.
To study batting consistency.

## Top Bowlers Analysis

Wicket information was extracted from the deliveries dataset.

Purpose:

To determine the most successful bowlers in IPL history.

## Boundary Analysis

Two separate analyses were performed:

Most Sixes

Players who hit the highest number of sixes were identified.

Purpose:

To identify aggressive power hitters.

Most Fours

Players with the highest number of boundaries were analyzed.

Purpose:

To identify technically sound batsmen capable of maintaining scoring momentum.

## Strike Rate Analysis

Strike rate was calculated using:

Strike Rate = (Runs Scored / Balls Faced) × 100

Only batsmen with at least 1000 IPL runs were considered to avoid small sample bias.

Purpose:

To compare scoring efficiency among established batsmen.

## Orange Cap Analysis

Season-wise highest run scorers were identified.

Purpose:

To determine batting dominance across different IPL seasons.

## Purple Cap Analysis

Season-wise highest wicket takers were identified.

Purpose:

To analyze bowling dominance across IPL seasons.

## Super Over Analysis

Matches involving Super Overs were analyzed.

Purpose:

To study the occurrence of highly competitive matches.

## Umpire Analysis

The frequency of umpire appearances was analyzed.

Purpose:

To identify the most experienced IPL umpires.

## Stage 4: Machine Learning Model Development

After completing EDA, a Machine Learning model was developed to predict IPL match winners.

## Feature Selection

The following features were selected:

Team 1
Team 2
Toss Winner
Toss Decision
Venue

## Target Variable:

Winner

These features were selected because they directly influence match outcomes.

## Encoding Categorical Variables

Since Machine Learning algorithms cannot process textual information directly, Label Encoding was used to convert categorical values into numerical form.

Examples:

Mumbai Indians → 7
Chennai Super Kings → 0
Train-Test Split

The dataset was divided into:

Training Data (80%)
Testing Data (20%)

Purpose:

Training data was used for learning patterns.
Testing data was used for evaluating model performance on unseen matches.

## Machine Learning Models Used

Two classification algorithms were implemented.

## 1. Logistic Regression

Logistic Regression was used as a baseline classification model.

Accuracy Achieved:

23.8%
## 2. Random Forest Classifier

Random Forest was implemented because it can capture complex non-linear relationships and generally performs well on categorical datasets.

Accuracy Achieved:

55.5%

After comparing both models, Random Forest was selected as the final prediction model.

## Winner Prediction Module

The final system allows users to provide:

Team 1
Team 2
Toss Winner
Toss Decision
Venue

The trained Random Forest model processes these inputs and predicts the probable winner of the IPL match.

## Key Findings
Most IPL teams prefer to field first after winning the toss.
Winning the toss alone does not guarantee match victory.
Mumbai Indians and Chennai Super Kings have consistently performed well.
A small number of players dominate batting and bowling statistics.
Venue and match conditions play a significant role in determining outcomes.
