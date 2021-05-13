
# Telecommunications Churn Predictiom

## Discovering which customers are most likely to churn, why, and how to focus efforts on retaining them

### Author: Jessica Forrest-Baldini

## Business Case

Telecom, a telecommunications company is interested in knowing why they're losing customers and how they can predict customers who are likely to churn so they can target marketing efforts to retain these customers. 

Since the cost of aquiring customers is much higher than the cost of maintaining them, and losing customers also means losing revenue, these efforts will increase their firm's profit and value. 

## Data

https://www.kaggle.com/becksddf/churn-in-telecoms-dataset

bigml_59c28831336c6604c800002a.csv

Filename changed to: telecom-churn-data.csv in this repository

## Contents 

- churn_classifier.ipynb - Project Notebook
- clf_functions.ipynb - Project Functions 
- telecom_churn_data.csv - Data
- README.md - Readme File
- Telecom-Churn-Prediction.pdf - Presentation Slides

## Methods 

I trained 3 classification models known to perform well in customer churn classification. There were:
- Bagged Tree
- Random Forest
- XGBoost

I tuned the models with optimal hyperparameters discovered using GridSearchCV. 

I conducted a full EDA on the dataset noting and exploring any patterns. I then looked at the top ranked feature importances from our best performing models and compared the two for patterns and insignts.

When turning the models I optimized for recall as we're mostly concerned with maximizing true positives and minimizing false negatives. I did however take into account the false positive rate as well making sure it wasn't so high that it might waste our efforts to focus on a large extra group of customers who are unlikely to churn.

## Results

### Models 

The top performing models were Random Forest and XGBoost. 

Random Forest had a recall of 87% and an accuracy of 93%
XGBoost had a recall of 85% and an accuracy of 96%

Note the higher accuracy with XGBoost was due to the lower false positive rate. 

!["Accuracy Scores"](figures/Accuracy%20Scores.png)

### Feature Importance

The top 3 most important features were the same for Random Forest and XGBoost, and those were:

  #1: Having an international plan 
  #2: Total charges
  #3: Customer service calls (# of)
  
!["Feature Importance"](figures/feat_rank_XGB.png)
  
### EDA Insights

We found that:

- Customers with international plans are more likely to churn, and that customers with international plans appeared to have slightly higher charges.
- Customers who had made more customer service calls were more likely to churn.
- When it came to charges there were two distinct modes of churners: those with significantly higher charges than non-churners, and those with lower charges than non-churners.

!["International Plan"](figures/international%20plan.png)
!["Customer Service Calls"](figures/customer%20service%20calls.png)
!["Total Charges"](figures/total%20charges.png)


## Recommendations

I recommend using XGBoost as it performs faster and has a clear pattern of feature importance, and also has comparable recall and fewer false positives (thus slightly higher accuracy) than Random Forest.

### Business

There are a few different groups that I want to make recommendations for. It seems we have 3 groups of churners:

- Those on an international plan
- Those with high charges
- Those who have made a high number of customer service calls

###  International Plan

Those with an international plan that churned had slightly higher charges. In future work I would want to find out exactly why people on international plans are churning. It could be that competitors have better plans or it could be that they moved back to another country. Are these customers traveling for work or here in the states temporarily? Do competitors have much more attractive and perhaps more cost effective international plans?

###  High Charges

This group is probably being lost to competitors. I would recommend looking at competitors plans. Do these customers go over their plan? If so I would recommend proactively offering a higher grade package to this customer group to save them money instead of them having high overage charges.

An alternative might be some type of booster package. Where if a customer goes over, they're given an add on package at a better rate than their overage, but still higher than their plan rate.

I would also recommend proactively letting these customers know when they're nearing an overage and offering them a plan that better fits their usage needs to prevent overages and thus high charges.

###  High Customer Service Calls

I know telecommunications companies have a special department for customers who want to cancel. They offer them more competitive plans, savings or offers. It would be good to train customer service representatives to make better offers early on. I understand there may be a tradeoff here between making the offer to more customers who may not churn and thus finding a balance between proactively retaining customers who might churn and making better offers to customers who may not churn would be important.

There wasn't an apparent relationship between total charges and customer service calls. However, charges of churners were bi-modal, so these could be averaging each other out. I will speak on this in the future work section.

I recommend the department that deals with cancellations proactively contact customers who have made more than 5 customer service calls as it seems that's where churn rate starts to significantly increase.

## Further Research

For future work I would recommend exploring the customer service calls of churners who made a high number of customer service calls.

I would also recommend researching more competitive plans that exist, especially for high usage and international plans.

As far as data science work, I would like to sus out the two groups of charges that churn (lower and higher) and discover why the lower group is churning and if there is any clear pattern there.

## Thank you!

For any additional questions, please feel free to connect with me at jlforrestbaldini@gmail.com or on LinkedIn at https://www.linkedin.com/in/jessica-forrest-baldini.

#### Social Preview Photo
<span>Photo by <a href="https://unsplash.com/@jupp?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Jonathan Kemper</a> on <a href="https://unsplash.com/s/photos/telecommunications?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>
