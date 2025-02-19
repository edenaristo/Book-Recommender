# Predicting the Rating of a Book Based on the User’s Age, Region, and Rating of Past Books Using Collaborative Filtering and K Nearest Neighbors

## SUMMARY OF THE PROJECT
In this project, our objective is to create a recommendation system model that is able to predict what books user prefer, based on historical data. This model utilize user-based collaborative filtering methods, with the aim to recommend books by using patterns of user ratings. The effectiveness of this model hinges on the quality and comprehensiveness of the underlying datasets. This project has been developed as an assignment for COMP20008 - University of Melbourne.

---

## DATA DESCRIPTIONS

This repository contains three main datasets and three optional sets related to books from the BX community. These datasets include information about books, ratings given by users, and user details.

### MAIN DATASETS

**BX-Books.csv**
- **ISBN**: International Standard Book Number, a unique identifier for books.
- **Book-Title**: Title of the book.
- **Book-Author**: Author(s) of the book.
- **Year-Of-Publication**: Year when the book was published.
- **Book-Publisher**: Publisher of the book.
- **Total Rows**: 18,185

**BX-Ratings.csv**
- **User-ID**: Unique identifier for users.
- **ISBN**: International Standard Book Number, a unique identifier for books.
- **Book-Rating**: Rating given by users to books.
- **Total Rows**: 204,146

**BX-Users.csv**
- **User-ID**: Unique identifier for users.
- **User-City**: City where the user is located.
- **User-State**: State where the user is located.
- **User-Country**: Country where the user is located.
- **User-Age**: Age of the user.
- **Total Rows**: 48,299

### EXTRA DATASETS

**BX-NewBooks.csv**
- **ISBN**: International Standard Book Number, a unique identifier for books.
- **Book-Title**: Title of the book.
- **Book-Author**: Author(s) of the book.
- **Year-Of-Publication**: Year when the book was published.
- **Book-Publisher**: Publisher of the book.
- **Total Rows**: 8,924

**BX-NewBooks-Ratings.csv**
- **User-ID**: Unique identifier for users.
- **ISBN**: International Standard Book Number, a unique identifier for books.
- **Book-Rating**: Rating given by users to books.
- **Total Rows**: 26,772

**BX-NewBooks-Users.csv**
- **User-ID**: Unique identifier for users.
- **User-City**: City where the user is located.
- **User-State**: State where the user is located.
- **User-Country**: Country where the user is located.
- **User-Age**: Age of the user.
- **Total Rows**: 8,520

---

## FILES

### preprocess_books.ipynb
This Jupyter Notebook contains all the preprocessing steps on BX-Books.csv dataset.
- Eliminating books with a publishing year of zero.
- Cleaning up duplicate ISBN entries.
- Normalising the capitalisation of book author names.
- Performing other essential data transformations.

### preprocess_user.ipynb
This Jupyter Notebook contains all the preprocessing steps on BX-Users.csv dataset. 
- Cleaning procedures including eliminating duplicate and non-integer user IDs.
- Processing and imputing missing regional data (city, state, and country) by filling in the blanks with NaN and using the data that is currently accessible.
- Outlines the way the user age data was cleaned and standardised, including:
  - How non-numeric characters were removed.
  - How ages were converted to integers.
  - How NaN was used to replace age numbers that were outside of range.
  - How records with NaN ages were finally eliminated to guarantee data quality.

### preprocess_ratings.ipynb
This Jupyter Notebook contains all the preprocessing steps on BX-Ratings.csv dataset. 
- Removing duplicates from the rating process.
- Verifying that all rating values fall between 1 and 10.
- Making sure that each rated ISBN is present in the BX-Books.csv dataset.
- Ensures that each ISBN can only be rated by the same user once. 

### complete_research.ipynb
This Jupyter Notebook captures the full research process from beginning to end. It creates a single workflow by integrating all preprocessing stages from the different notebooks for books, users, and ratings.
- Prepares the data.
- Applies the user-based collaborative filtering algorithm.
- Closes with an assessment of the model's performance, including conclusions and insights.

### report.pdf
This document is the summary and analysis of everything in this repository. This report includes every thinking behind every decisions made in this project.
There is also a complete documentation on the dataset, preprocessing technique, machine learning model developed, and the effectiveness of the model.


---

## USAGE

In order to achieve the research results, users only need to run the complete_research.ipynb file (run all). 

The preprocessing files are only intended to show how the thinking behind the preprocessing functions (in complete_research.ipynb) are done. This can be done by running each file (run all).
