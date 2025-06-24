### *What are SHAP Values?*

Shap values come from game theory, and are used to distribute the outcome of a game among its players. For example, if four colleagues join a 
coding competition and win a $2000 prize, calculating Shap values would explain **how much of the prize each person has earned based on their contributions**. 

>[!IMPORTANT]
>In the context of machine learning, players are replaced with features/ attributes and the game outcome is replaced with the model’s prediction (predicted probability). Doing so allows us to **quantify how much each of the features contributed to the prediction** of a single record. Shap values are calculated through an equation known as **marginal contribution**.

### *What is Marginal Contribution?*

Marginal Contribution represents the average difference in the model's output (predicted probability) when a feature is included and excluded from every possible subset of features during prediction. As a result, calculating Marginal Contribution becomes increasingly difficult as the number of features/ attributes increases. To mitigate this complexity, Shap values are often estimated instead of directly calculated. The original [NeurIPS Paper](https://papers.nips.cc/paper_files/paper/2017/hash/8a20a8621978632d76c43dfd28b67767-Abstract.html) discusses the estimation process thoroughly.

### *What is Mean Absolute SHAP Value?*

Calculating or estimating Marginal Contribution results in a table of Shap values with the exact dimensions as your original data. The Mean Absolute Shap Value of a feature is the sum of absolute shap values in the feature’s column divided by the total number of records. Mean Absolute Shap Values describe Feature Contribution similar to the way that Mean Decrease in Impurity (MDI) describes Feature Importance.


In general, It's desirable that a machine learning model does not make predictions from biases that may exist in sensitive features such as gender or ethnicity. It’s especially important when models are used in downstream decision making. Fairlearn has a framework to assess and improve model fairness for this exact reason.

*What is the idea behind Fairlearn?*

>Fairlearn allows us to group records based on a sensitive feature such as gender, examine our model’s performance for each group (ie. Male/ Female), and finally calculate group-wise comparisons to see if there is a disparity in model performance between the groups.

>There are three main group-wise metrics used to measure disparity in model performance, Demographic Equality, Equal Opportunity, and Equal odds. Each metric examines an aspect of the model’s performance across each group. The metric that best fit’s our data is Equal Odds. 

*What is the Equal Odds metric?*

>Equal Odds examines whether the TPR and FPR are consistent across the groups. This is important to fraud detection since we mainly evaluate TPR at a fixed 5% FPR. We can calculate the equal odds in absolute or proportional sense.



