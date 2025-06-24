## *What are SHAP Values?*

Shap values come from game theory, and are used to distribute the outcome of a game among its players. For example, if four colleagues join a 
coding competition and win a $2000 prize, calculating Shap values would explain **how much of the prize each person has earned based on their contributions**. 

>[!IMPORTANT]
>In the context of machine learning, players are replaced with features/ attributes and the game outcome is replaced with the model’s prediction (predicted probability). Doing so allows us to **quantify how much each of the features contributed to the prediction** of a single record. Shap values are calculated through an equation known as **marginal contribution**.

## *What is Marginal Contribution?*

Marginal Contribution represents the average difference in the model's output (predicted probability) when a feature is included and excluded from every possible subset of features during prediction. As a result, calculating Marginal Contribution becomes increasingly difficult as the number of features/ attributes increases. To mitigate this complexity, Shap values are often estimated instead of directly calculated. The original [NeurIPS Paper](https://papers.nips.cc/paper_files/paper/2017/hash/8a20a8621978632d76c43dfd28b67767-Abstract.html) discusses the estimation process thoroughly.

## *What is Mean Absolute SHAP Value?*

Calculating or estimating Marginal Contribution results in a table of Shap values with the exact dimensions as your original data. The Mean Absolute Shap Value of a feature is the sum of absolute shap values in the feature’s column divided by the total number of records. Mean Absolute Shap Values describe Feature Contribution similar to the way that Mean Decrease in Impurity (MDI) describes Feature Importance.

## *Fairness & Fairlearn*

It's critical that a machine learning model does not make predictions from biases that may exist in sensitive features such as gender or ethnicity. It’s especially important when models are used in downstream decision making. Fairlearn has a framework to assess and improve model fairness for this exact reason.

Fairlearn allows us to group records based on a sensitive feature such as gender, examine our model’s performance for each group (ie. Male/ Female), and finally calculate group-wise comparisons to see if there is a disparity in model performance between the groups. There are three main [group-wise metrics](https://fairlearn.org/main/user_guide/assessment/common_fairness_metrics.html#) used to measure disparity in model performance, Demographic Equality, Equal Opportunity, and Equal odds. Each metric examines an aspect of the model’s performance across each group.
