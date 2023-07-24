# Weather Classification- Good Day for a BBQ?

### Lynn Anderson


# Business Understanding

All Fired Up is a renowned barbeque and grill restaurant located in London, UK. They serve food from their kitchen every day, and recently started offering an outdoor area featuring freshly grilled food from hardwood lump charcoal. Their outdoor charcoal grilled foods have quickly become a huge hit, and on certain days get lots more business. However, on other days, hardly any people line up, or the grills fail to run properly. Weather seems to be a huge factor. Setting up the outdoor charcoal grills takes a lot of time and resources, so it is only worth it to fire up the charcoal and run the grill if it is nearly certain to be a nice day for barbequing. However, they also lose out on profits by not running the outdoor grill, since it attracts many more customers and they can charge a higher price. 

Thus, it will be important for my classification model to have a very low rate of false positive errors (ie a predicted 'good' day that is actually not suitable for a bbq), but not entirely at the expense of a large number of false negatives. For my evaluation metric, I am primarily concerned with the F1 score, since it represents the mean of the precesion and recall, and is a better metric on imbalanced datasets than accuracy or AUC. I will also be considering precision when evaluating models, since a high precision indicates the model predicts few false positives. ability to both capture positive cases (recall) and be accurate with the cases it does capture (precision) 


# Data 

The dataset consisted of two csv files- one containing records for in different cities, and the other with boolean values for whether it was a good bbq day. Both datasets contained 3,654 entries, each representing a day that weather information was recorded. I was only interested in data related to the Heathrow meteorological stations, so removed irrelevant columns and merged the two dataframes before performing any exploratory analysis or modeling. 

![lvg_room](https://github.com/lalynjay/Housing_Prices_Analysis/blob/alt/images/lvg.png)


# Modeling

Multiple different classification algorithms were explored- logistic regression, K-Nearest Neighbors, and Decesion Tree models were investigated, tuned, and evaluated. The F1 score was the primary metric used for evaluation. A grid search was used to find the optimal random forest model. 


# Evaluation

All models based on decision trees outperformed other types of models. The basic decesion tree, more complex random forest had F1 scores of 100. Since the basic decision tree was just as good and is less computationally expensive, it is the best model for solving this problem.


# Conclusions

Max temperature and precipitation are by far the most important factors to consider when deciding whether or not to fire up the outdoor charcoal grills. Since temperature for a given day is easier to predict than knowing if it will rain, further attention should be directed towards weather models that accurately predict if the area will receive significant rain. 


# Limitations and Next Steps

Temperature for a given day is easier to predict than knowing if it will rain. Wind is likely a factor. Data is older, climate change and shifting weather patterns may influence. 


# For More Information

See the full analysis in the [Jupyter Notebook](https://github.com/lalynjay/Housing_Prices_Analysis/blob/alt/Housing_Prices_Analysis.ipynb) or review [this presentation](https://github.com/lalynjay/Housing_Prices_Analysis/blob/alt/Housing_Prices_presentation.pdf)

For additional info, contact Lynn Anderson at lalynjay@gmail.com

Repository Structure

├── data

├── images

├── README.md

├── weather_classification_presentation.pdf

└── weather_classification.ipynb

