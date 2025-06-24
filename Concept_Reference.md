### *What are SHAP Values?*

Shap values come from game theory, and are used to distribute the outcome of a game among its players. For example, if four colleagues join a 
coding competition and win a $2000 prize, calculating Shap values would explain **how much of the prize each person has earned based on their contributions**. 

>[!IMPORTANT]
>In the context of machine learning, players are replaced with features/ attributes and the game outcome is replaced with the model’s prediction (predicted probability). Doing so allows us to **quantify how much each of the features contributed to the prediction** of a single record. Shap values are calculated through an equation known as **marginal contribution**.

### *What is Marginal Contribution?*

Marginal Contribution represents the average difference in the model's output (predicted probability) when a feature is included and excluded from every possible subset of features. The equation below has two components, 1. An assigned weight (leftmost component), and 2. A difference in predictions (rightmost component).

  - F is the set of all features
  - S is the feature who’s marginal contribution we calculate 
  - S ⊊ F  are all the subsets of feature S

*What is Mean Absolute SHAP Value?*

>After calculating marginal contribution of each feature and record, you have a table of Shap values with the exact dimensions as your original data. The Mean Absolute Shap value of a feature is the sum of absolute shap values in the feature’s column divided by the total number of records. This is the Shap equivalent of a Random Forest model’s feature importance score.
 
*What are Dependence Plots?*

>To understand a feature’s importance in a model, it is necessary to understand both how changing that feature impacts the model’s output, and also the distribution of that feature's values. The dependency plot helps us visualize these relationships.



>In general, It's desirable that a machine learning model does not make predictions from biases that may exist in sensitive features such as gender or ethnicity. It’s especially important when models are used in downstream decision making. Fairlearn has a framework to assess and improve model fairness for this exact reason.

*What is the idea behind Fairlearn?*

>Fairlearn allows us to group records based on a sensitive feature such as gender, examine our model’s performance for each group (ie. Male/ Female), and finally calculate group-wise comparisons to see if there is a disparity in model performance between the groups.

>There are three main group-wise metrics used to measure disparity in model performance, Demographic Equality, Equal Opportunity, and Equal odds. Each metric examines an aspect of the model’s performance across each group. The metric that best fit’s our data is Equal Odds. 

*What is the Equal Odds metric?*

>Equal Odds examines whether the TPR and FPR are consistent across the groups. This is important to fraud detection since we mainly evaluate TPR at a fixed 5% FPR. We can calculate the equal odds in absolute or proportional sense.



