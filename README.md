# Building-an-MMA-Fight-Analyzer-Using-Machine-Learning
### A Study into the In-Fight Factors Affecting Chances of Victory (or Defeat)
![Image description](https://pmcvariety.files.wordpress.com/2018/10/ufc.jpg?w=1000)


As a Mixed Martial Arts fan, I thought it would be interesting to analyze fight data to see what insights could be drawn and inferences made as to the in-fight factors affecting the outcome.

I found a dataset on Kaggle containing data on nearly 3000 fights that took place between 2013-17 in the Ultimate Fighting Championship (UFC), a US-based MMA promotion. After removing rows with mostly missing data, the dataset was reduced to 1791 rows. I then decided to remove fights that ended in draws and no-contests, which further reduced the size of the final dataset to 1762.                                 
## The Task

The dataset consisted of some 453 features representing characteristics both of the fight and of one of the fighters. These ranged from variables such as fighter age, current winning streak, and fighter height and weight, to factors like ground control time in each round, submission attempts, and significant strikes attempted and landed to various parts of the body. The goal of the study was to find out whether, given these relevant data from one side of the fight, a model could be trained to determine whether that fighter won or lost.

Since the majority of the available variables concerned events and statistics that became known during the fight (as opposed to before it), this project was intended to be a backward-looking, inferential analysis designed to weigh the most important factors determining victory in an MMA fight.

## The Method

Three different methods were used to select features:

* Pearson correlation (as seen in Python's standard correlation matrix)

* ANOVA Filter with SelectKBest

* Chi-square with SelectKBest.

For each method, each Supervised Learning model was run using 8-fold cross-validation to highlight any overfitting. The raw accuracy, F1 score and standard deviation of the accuracy were then plotted against the number of variables used. In this way I was able to compare and evaluate the three feature-selection methods for predictive accuracy, and chart the change in accuracy with this increasing number of variables.

## Results

Of the approaches tried, the best combination of ML Model and Feature-Selection method was XGBoost with either Pearson Correlation or ANOVA with SelectKBest. Both combinations were able to reach a raw classification accuracy over 80%, with a peak F1 score of around 85%, using approximately the 60 best variables. Most model combinations were able to achieve around 65% accuracy and 70% F1 score with as few as 5 variables used. Of all models, only the KNN Classifier and Support Vector Classifier failed to gain in accuracy with the addition of more input variables. The SVC actually performed progressively worse as more variables were added. In all cases, χ2 with Select K-Best underperformed the other two Feature-Selection methods.


The standard deviation of the (8-fold) cross-validated accuracy showed the most variation in the case of the Random Forest Classifier. This is an obvious and unsurprising indication that a significant amount of overfitting was occurring at least on some iterations.
