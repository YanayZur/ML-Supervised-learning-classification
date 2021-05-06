# ML-Supervised-learning-classification
## The Problem
* I received a database with data about website visitors, their characteristics, and their decision whether to make a purchase or not.
* Depending on the given data, I was asked to tell, for new visitors, whether a purchase will be made or not.
* I produced my prediction using **supervised learning** techniques.

## My Work
### Exploratory Data Analysis (EDA):

* There are 12 feeatures in total, of which one is an input (tag).
* All features are balanced in terms of mean, median and standard deviation except of two: *target_product_description_length* and *target_product_price*. I applied the 'RobustScaler' on these two features.
* Missing entries for some feature were replaced with the median value of that feature across the entire dataset.
* In terms of tags - there are 3 times more tags with a value of 0 compared to tags with a value of 1.
* I did not find a significant correlation between features.
* Categorical values are arbitrarily encoded with numeric values.

### Modeling and prediction:

* Training set is randomly splitted to 70% training and 30% test.
* The models I tested are
1. KNN Classifier
2. Logistic Regression Classifie
3. Random Forest Classifier
4. Bernoulli Naive Bayes
* For each model I plotted its accuracy metrics as well as a confusion matrix.

* **The model with the highest percentage of accuracy among the models tested is-Random Forest Classifier, with 82% success rate (over the test set)**

* After selecting the model, we applied it to the data without the tags and exported the result to a file.

### Final Conclusion:

#### Future explorations

* The feature *target_product_price_color* is highly biased toward 'red', which suggests that red colored price attracts more activity to the website. We should validate/invalidate this hypothesis (possibly using an A/B testing).
* Similarly, data is biased toward short delivery time.

#### Conclusions

* The success rate of the models I have tested ranges between 75% to 82%, with Random Forest gains the maximal success rate.
* The features that exposed most contribution to the final decision in that model are *age*, *target_product_price*, and *target_product_description_length*, which suggests that more attention should be paid to these, and maybe try to collect more data which is not collected thus far.
* We applied the selected model to the UNSEEN data, and out of 20,000 shows we received that in almost 18% of the times a purchase will be made. A figure that is lower than the figure of the data that was initially provided to us (about 26% of the data of 80,000 instances).
