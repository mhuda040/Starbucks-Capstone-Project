# CAPSTONE PROJECT - Starbucks-Capstone-Project

## Project Overview / Motivation

This project will analyze simulated data from the Startbucks mobile app regarding offers and promotions.  The dataset for this project contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks.

Please note that the dataset is not the real dataset used for the Starbucks mobile app, as Starbucks sells a variety of products.  The dataset contains only one product.

We will analyze and clean the data, then perform modeling using a variety of classifiers to determine what offers customers would respond to and the scores that justify those responses.

## Required Files

- Jupyter Notebook
  - `Starbucks_Capstone_notebook.ipynb`:  Main file that contains the necessary code to build our recommendation engine 

- HTML files
  - `Starbucks_Capstone_notebook.html`:  HTML version of main Jupyter Notebook file

- Dataset files (these should not be modified in any way; also these files are not used in the actual Starbucks mobile app)
  - `profile.json`:  JSON file that contains demographics of Rewards program users:
    - age (int) - age of the customer
    - became_member_on (int) - date when customer created an app account
    - gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
    - id (str) - customer id
    - income (float) - customer's income
  
  - `portfolio.json`:  JSON file that contains Offers sent during a 30-day period:
    - id (string) - offer id
    - offer_type (string) - type of offer ie BOGO, discount, informational
    - difficulty (int) - minimum required spend to complete an offer
    - reward (int) - reward given for completing an offer
    - duration (int) - time for offer to be open, in days
    - channels (list of strings)

  - `transcript.json`:  JSON file that contains Events:
    - event (str) - record description (ie transaction, offer received, offer viewed, etc.)
    - person (str) - customer id
    - time (int) - time in hours since start of test. The data begins at time t=0
    - value - (dict of strings) - either an offer id or transaction amount depending on the record

Please note that the JSON files are stored in a ZIP file; you will need to unzip this file and extract the JSON files in a directory called 'data', in order for the Starbucks_Capstone_notebook.ipynb file to run properly.

## Installation

Must have Python 3 or higher to run the required files.

Must have the newest version of pandas to read in the transcript.json file correctly; previous versions of pandas will require going into the workspace terminal and running the following command:  `conda update pandas`

Must unzip the data.zip file in a directory called 'data'

Must include the following libraries in the Starbucks_Capstone_notebook.ipynb file:
- numpy
- pandas
- matplotlib
- sklearn
- seaborn
- datetime
- warnings
- json

## Instructions

Run the Starbucks_Capstone_notebook.ipynb file by going to the terminal, selecting Cell, then Run All.  If using a different Jupyter Notebook, please ensure the above installation criteria are met and that there is an option to run all Python cells in the notebook.

## Summary Highlights

- Majority of Starbucks customers in the dataset were male, had a higher income, and were more likely to respond to an offer than females.
- In modeling the transcript data, K-Nearest Neighbors performed poorly for BOGO and Discount offers
- Decision Tree was the best classifier for the Training data; AdaBoost was the best classifier for the Test data
- Decision Tree is best for Discount; AdaBoost is best for BOGO
- Train and Test scores for AdaBoost were similar in both BOGO and Discount
- The score for Random Forest classifier in the Test data is slighly leaned toward BOGO, but only by a small margin

## Acknowledgements

This project was prepared as part of the Udacity Data Scientist nanodegree program.  Special thanks to Starbucks for providing the required JSON files for the data exploration and analysis.  Additional thanks to Udacity for providing the template code for the Jupyter Notebook.
