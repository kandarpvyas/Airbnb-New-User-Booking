# Airbnb-new-user-booking
Predicting countries which will be booked by Airbnb users as their first booking.
• Analyzed Airbnb customer data of over 0.2 million to solve a multi-label, class-imbalance classification problem. 
• Preprocessed the data using techniques like predict missing values using weighted-imputation, Binning, Stratified Sampling,Binarization of categorical data.
• Designed a model to predict the country of destination of users on Airbnb using Keras Artificial Neural Network (ANN), XGBoost Classifier,Naïve Bayes algorithm,Random forest classifier and KNN classifier.

# Airbnb Kaggle Competition: *New User Bookings*

This repository contains the code developed for the [Airbnb's Kaggle
competition][competition]. It's written in **Python**, some in the form
of **Jupyter Notebooks**, and other in pure Python 3.

The entire run should not take more than 4 hours(thanks to the parallel
preprocessing) in a modern/recent computer, though you may run into memory
issues with less than 8GB RAM.

Feel free to contribute to the code or open an issue if you see something wrong.

[competition]: https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings


## Description

New users on *Airbnb* can book a place to stay in 34,000+ cities across 190+
countries. By accurately predicting where a new user will book their first
travel experience, *Airbnb* can share more personalized content with their
community, decrease the average time to first booking, and better forecast
demand.

In this competition, the goal is to predict in which country a new user
will make his or her first booking. There are **12** possible outcomes of the
destination country and the datasets consist of a list of users with their
demographics, web session records, and some summary statistics.

## Data

You need to download `train_users_2.csv`, `test_users.csv` and `sessions.csv`
files and unzip them into the 'data' folder.

**Note**: Since the train users file is the one re-uploaded by the competition
administrators, rename `train_users_2.csv` as `train_users.csv`.

[rules]: https://www.kaggle.com/c/airbnb-recruiting-new-user-bookings/rules

## Main Ideas

1. The provided datasets have lot of NaNs and some other *random* values, so, a
good preprocessing is the primary key to get a good solution:
    - Replace *-unknown-* values with NaNs
    - Clean age values
    - Extract day, weekday, month, year from `date_account_created`
    and `timestamp_first_active`
    - Add number of missing values per user
    - General user session information:
        - Number of different values in `action`, `action_type`,
        `action_detail` and `device_type`

2. That kind of classification task works nicely with tree-based methods, I
used `xgboost` library and the Gradient Boosting Classifier that provides along
`scikit-learn` to make the probabilities predictions.

## Requirements

To replicate the findings and execute the code in this repository you will need
basically the next Python packages:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org/)
- [Jupyter](http://jupyter.org/)
- [SciKit-Learn](http://scikit-learn.org/stable/)
- [Matplotlib](http://matplotlib.org/)
- [Keras Sequential Model](https://keras.io/models/sequential/)
- [Tensorflow](https://www.tensorflow.org/)



## Resources

- [XGBoost Documentation](https://xgboost.readthedocs.org) - A library designed
and optimized for boosted (tree) algorithms.
