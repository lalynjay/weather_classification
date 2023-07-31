# Weather Classification- Good Day for a BBQ?

### Lynn Anderson

# Overview

The aim of this project was to find the best classification model for predicting good bbq weather. Regression and classification models are both supervised learning algorithms that use one or more independent variables to build models that predict some response. While regression is useful when a target variable is continuous, classification is used for situations where the target variable is labelled into two or more discrete values. In this case, the target variable had two values- True and False- indicationg whether or not that specefic day was suitable weather for an outdoor bbq. In addition to building a model that could best predict the outcomes, I aimed to find the most important weather factors in determining the outcome.


# Business Understanding

All Fired Up is a renowned barbeque and grill restaurant located in London, UK. They serve food from their kitchen every day, and recently added on an outdoor area featuring freshly grilled food from hardwood lump charcoal. Their outdoor charcoal grilled foods had quickly become a huge hit, and on certain days got lots of business. However, on many other days, hardly any people line up outside, or the grills failed to run properly. Weather seemed to be a huge factor, so they wanted to know more about what weather is ideal for running the outdoor bbq area. Setting up the outdoor charcoal grills take a lot of time and resources, so it is only worth it to fire up the charcoal and run the grill if it is going to be a nice day for barbequing. Otherwise, there is a significant loss on the days they prepare for outdoor grilling but are unsuccessful. However, they also lose out on profits by not running the outdoor grill, since it attracts many more customers and they can charge a higher price. 

Thus, it was be important for my classification model to have a very low rate of false positive errors (ie a predicted 'good' day that is actually not suitable for a bbq), but not entirely at the expense of a large number of false negatives. For my evaluation metric, I was primarily concerned with the F1 score, which represents the harmonic mean of the precesion and recallThe F1 score reflects the model's ability to ability to both capture positive cases (recall) and be accurate with the cases it does capture (precision). Furthermore, it is a better metric on imbalanced datasets than accuracy or AUC. I  alo be considered precision when evaluating models, since a high precision indicates the model predicted few false positives. 


# Data 

The dataset consisted of two csv files- one containing records for in different cities, and the other with boolean values for whether it was a good day for an outdoor bbq. The data was sourced from https://www.kaggle.com/datasets/thedevastator/weather-prediction. Both files contained 3,654 entries, each representing a day that weather information was recorded. Of those, 2,785 were False (not a god day for a bbq) and 869 True. The dates span between 2000 and 2010, and initially contained information for 18 different European cities. I was only interested in data related to the Heathrow meteorological stations, so removed irrelevant columns and merged the two dataframes before performing any exploratory analysis or modeling. 

![outcomes](https://github.com/lalynjay/weather_classification/blob/main/images/outcomes.png)

False outcomes were 3 times more common than true ones.

![months](https://github.com/lalynjay/weather_classification/blob/main/images/months.png)

Summer months had way more good days, and some winter months had none.


# Modeling

Multiple different classification algorithms were explored- logistic regression, K-Nearest Neighbors, a basic Decision Tree, and Random Forest models were investigated, tuned, and evaluated. The F1 score was the primary metric used for evaluation. 

![all_features](https://github.com/lalynjay/weather_classification/blob/main/images/feature2.png)

An optimal model based on a relatively simple grid search on a Random Forest found the above features most important.


![features](https://github.com/lalynjay/weather_classification/blob/main/images/feature_1.png)

The basic decision tree model found precipitation and max temp as the primary determining factors. 



# Evaluation

The basic decision tree model, and subsequent more complex models based off decision trees- the random forest and grid search tuned random forest- far outperformed the logistic regression and K-Nearest Neighbors models. All the models based off decision trees had an F1 score of 1, which indicated those models perfectly predicted every outcome. The best logistic regression model had an F1 score of .95, while the best KNN model was only .84.

While decision trees can often tend to overfit training data and be more affected by outliers, in this case the decision tree performed just as well as the more complex models. Since a random forest or bagged tree is much more computationally expensive than a simple decision tree, in this case the decision tree is the best model in terms of overall performance and efficiency. 

![features](https://github.com/lalynjay/weather_classification/blob/main/images/tree.png)

As is evident again in this visualization of the basic decision tree, max temp and precipitation were the primary factors in determining the outcome.



# Conclusions

*  The basic decision tree is the best model for accurately predicting good bbq weather. 


*  Max temperature and precipitation are by far the most important factors to consider when deciding whether or not to fire up the outdoor charcoal grills. 


*  Check the forecast, ideally the morning of, and make a call based on the temperature and precipitation forecasts. 


*  Finally, due to there being almost no good days November-March, consider closing the outdoor area and tidying away the grills for the winter months.


# Next Steps and Limitations

*  Further research should be done to determine the relationship between "percent chance of precipitation" and outcome. 


*  Wind is likely to be a factor, but was not represented in this dataset. 


*  Finally, it is worth noting that the data is from over a decade ago- climate change and shifting weather patterns may influence current and future predictions. 


# For More Information

See the full analysis in the [Jupyter Notebook](https://github.com/lalynjay/weather_classification/blob/main/weather_classification.ipynb) or review [this presentation](https://github.com/lalynjay/Housing_Prices_Analysis/blob/alt/Housing_Prices_presentation.pdf)

For additional info, contact Lynn Anderson at lalynjay@gmail.com

Repository Structure

├── data

├── images

├── README.md

├── weather_classification_presentation.pdf

└── weather_classification.ipynb

