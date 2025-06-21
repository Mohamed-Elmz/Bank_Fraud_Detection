*What are SHAP Values?*

>Shap values come from game theory, and are used to distribute the outcome of a game among its players. For example, if four colleagues join a 
coding competition and win a $2000 prize, calculating Shap values would tell us **how much of the prize each person has earned based on their contributions**. 

*SHAP Values in ML*

>In the context of machine learning, players are replaced with features and the game outcome is replaced with the model’s prediction (predicted probability). Doing so allows us to **quantify how much each of the features contributed to the prediction** of a single record. Shap values are calculated through an equation known as marginal contribution.

*What is Marginal Contribution?*

>Marginal Contribution represents the average difference in the model's output (predicted probability) when a feature is included or excluded from every possible subset of features. The equation below has two components, 1. An assigned weight (leftmost component), and 2. A difference in predictions (rightmost component).

