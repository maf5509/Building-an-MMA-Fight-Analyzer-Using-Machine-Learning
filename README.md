# Building-an-MMA-Fight-Analyzer-Using-Machine-Learning
### A Study into the In-Fight Factors Affecting Chances of Victory (or Defeat)
![Image description](https://pmcvariety.files.wordpress.com/2018/10/ufc.jpg?w=1000)


As a Mixed Martial Arts fan, I thought it would be interesting to analyze fight data to see what insights could be drawn and inferences made as to the in-fight factors affecting the outcome.

I found a dataset on Kaggle containing data on nearly 3000 fights that took place between 2013-17 in the Ultimate Fighting Championship (UFC), a US-based MMA promotion. After removing rows with mostly missing data, the dataset was reduced to 1791 rows. I then decided to remove fights that ended in draws and no-contests, which further reduced the size of the final dataset to 1762.                                 
## The Task

The dataset consisted of some 453 features representing characteristics both of the fight and of one of the fighters. These ranged from variables such as fighter age, current winning streak, and fighter height and weight, to factors like ground control time in each round, submission attempts, and significant strikes attempted and landed to various parts of the body. The goal of the study was to find out whether, given these relevant data from one side of the fight, a model could be trained to determine whether that fighter won or lost.

Since the majority of the available variables concerned events and statistics that became known during the fight (as opposed to before it), this project was intended to be a backward-looking, inferential analysis designed to weigh the most important factors determining victory in an MMA fight.
