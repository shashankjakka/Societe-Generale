
## Predict Fraudulent Transactions

**Feature Selection and Engineering**

Since the features are all anonymised, cleaning and transforming the features proved to be a crucial part in this problem.<br />

The categorical features from cat_vars_20 are found to be a one hot vectors of only 3 features , so different approaches has been tried like label encoding them instead of one hots but one hots proved to be efficient here.<br />
    
One big problem was the High Cardinality of some of the Categorical Variables and New Labels in some features in test data.<br />

• **Features with High Cardinality and Test data has New Labels:**<br />
The labels are encoded with the popularity of that label in both train and test data.<br />
Ex: The label ‘gf’ in cat_var_1 repeated for 365237 times in both train and test data so it is encoded with the values 365237.<br />
• **Features with High Cardinality and Test data has NO New Labels:**<br />
The labels are encoded with weight of evidence.  <br />
W O E = I n ⎛ Pi / T P ⎞     i ⎜⎝ N i / T N ⎟⎠<br />
• Where TP and TN are Total positives and Total Negatives<br />
• P and N are number Positives and Negatives for a Specific label in a feature.<br />
 
 A nice characteristic of this transformation is that a label with a less than average fraud rate will have a negative value, and a higher than average fraud rate will lead to a positive transformed value.<br />
 
• **Features with Less Cardinality:**<br />
They have been converted into one hot vectors.<br />

**Modeling**

Tuned Random Forest,Xgboost and Lightgbm have been separately trained and those with a score of above 0.7365 have been averaged ( ensembled ) to improve the score to over 0.7373.<br />
