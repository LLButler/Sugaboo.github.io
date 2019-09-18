---
layout: post
title:      "Predicting wine"
date:       2019-09-18 04:17:44 +0000
permalink:  predicting_wine
---

Wine has a vast and diverse history spanning eons.  Fermented from grapes, wine has played a pivotal role in religions, culture and society in general.  Wine is complex and diverse as every person on this planet.  There are red wines, white times, rose, mead, etc.  What one enjoys in drinking a glass of wine, another might find not.  There are multiple sensory attributes that make wine so complex, astringency, texture, body, smell, etc.  So, can analyzing these attributes help one determine if a wine their drinking is red or white (assuming you’re not visually looking at it)?  Additionally, how can one analyze these attributes to get a better understanding of its quality from a statistical aspect?  The aim of this capstone will look at just that.  

The crux of this capstone will be can using machine learning and deep learning to predict the type of wine (either red or white) from features found within the dataset.  Additionally, methods for this analysis consists of exploratory data analysis (EDA), and categorizing wine into categories and looking at statistical analyses of each group.

So, like all previous data science analyses, the OSEMN framework was utilized.  OSEMN refers to the following: 
*  O — Obtaining our data 

*  S — Scrubbing / Cleaning our data

*  E — Exploring / Visualizing our data will allow us to find patterns and trends

*  M — Modeling our data will give us our predictive power as a wizard

* N — Interpreting our data

I obtained my wine dataset from the University of California, Irvine (UCI), which consisted of a red and white wine dataset.  There were twelve features (or columns) and the dataset between the two are imbalanced (1599 rows for red wine dataset, 4898 rows for white wine dataset).  I decided to break up my capstone into a few different Jupyter Notebooks to maintain a clean look.  In Jupyter Notebook #1, I loaded the libraries (Pandas, MatPlotLib, Seaborn, etc.), and just began my initial analyses.  Luckily there were no null values to stress about, and both sets of data were clean with matching features.  Looking solely at the red wine dataset, it consisted of 8 quality categories.  The quality feature, which was based on sensory data was a score between 0-10.  I was interested primarily in this feature since it would drive my analyses for this capstone project.  Using Seaborn, I ran `.counterplot()` to compare quality against a few features.  First off, the red wine categories were in a normal, distribution, which was great. I did not notice any strong relationships with red wine quality and the dependent variables. In order to determine the dependent variables better with a correlation matrix. However, I do notice that as citric acid, alcohol and sulphates increase as red wine quality increase.  I did the same for white wine and there really are no clear trends as white wine quality increases. Like red wine, I believe a correlation matrix would better help to understand the relationship between features.

![(https://imgur.com/BA9eDka)]
Red wine counterplot

![(https://imgur.com/XSa64Wa)]
Citric acid countplot_red

![(https://imgur.com/Zpbv1CT)]
Sulphate countplot_red

![(https://imgur.com/mCC0slH)]
White wine countplot

![(https://imgur.com/H3jZhbA)]
Citric acid countplot_white

![(https://imgur.com/3ShV6S6)]
Sulphate countplot_white

In Jupyter Notebook #2, I merged both datasets together and separated them into quality classes (i.e. – low, medium and high quality).  I was curious about the descriptive stats of each quality class, a noticed a few trends.  The highlights from descriptive statistic of wine quality class were the following: mean total sulfur dioxide and residual sugar content seems to be much higher in white wines than in red wines; citric acid is more present in white wines, while fixed acidity, volatile acidity and sulphates are more present in red wine; and red wines have double concentration of chlorides then white wines.  Using Seaborn’s `.distplot()` and `.boxplot()`, I compared dependent features to the independent feature (quality).  For instance, looking at fixed acidity against quality showed a fairly symmetric distribution with a long tail. The box plots showed medians for many quality categories are almost similar, along with multiple.  Overall, many features had a normal distribution which was skewed to the right and box plots of each varied.  

![(https://imgur.com/bkek0WR)]
Fixed acidity distplot

![(https://imgur.com/SyorCE1)]
Fixed acidity boxplot


Moving onto the wine quality and wine quality classes correlation and pairplot in Seaborn, the following trends were observed with wine quality: 

* Total (70%) and free (47%) sulfur dioxides have the highest correlation with white wines.

*	Free sulfur dioxide is a part of total sulfur dioxide and thus they have the highest correlation (72%). That represents collinearity that could be a problem for some models and free sulfur dioxide might need to be dropped later.

*	The volatile acid (-65%) and chlorides (-51%) have a negative correlation with color. This indicates a tendency to red wines classification.

*	The residual sugar has 50% relation with total sulfur dioxide and 40% with free sulfur dioxide. This is an indication that more sulfur dioxide is added to wines with higher sugar content to prevent secondary fermentation of remaining sugar.

*	Density has a relatively high negative correlation to alcohol (-69%). This is confirmed by the decreasing linear trend from left to right. Density also has a relatively high positive correlation to residual sugar (55%), which is reinforced by two white wine outliners.

*	Sulphates, chlorides, fixed acidity and volatile acidity in red wine seem to be higher than in white wine.

*	Residual sugar, total sulfur dioxide and citric acid seem to be higher in white wines as compared to red wine.

Jupyter Notebook #3, analyzed statistical trends between red and white wines.  Multiple types of statistics were run in Jupyter Notebook.  For instance, density has a relatively high negative correlation with alcohol.  Moreover, total sulfur dioxide and residual sugar content seem to be much higher in white wines than in red wines. I selected total sulfur dioxide against quality class analyzed Ordinary Least Squares (OLS) Regression.  While it was helpful to view the means, standard deviations, p values and F statistics for red and white wines, I was eager to start the next leg of my analyses (i.e. – machine learning). 

Now moving onto the actual pièce de résistance, predicting red or white wines!  In Jupyter Notebook #4, this was done using machine learning models.  I set up my train/test split (ratio: 80/20 split) data and focused on classification for my predictive modeling.  Additionally, I distinguished red wines with a value of 1 and white wines with a value of 0.  I choose to run the following: K-Nearest Neighbors (kNN), Logistic Regression, Support Vector Machine (SVM), Decision Tree and Random Forest. These models are examples of Supervised machine learning. Supervised machine learning is a method that enables the machine to classify and predict objects, problems or situations based on labeled data. With this type of model, your data is labeled, direct feedback is given, and the machine predicts the output.

With each predictive model, confusion matrices would be needed. Confusion matrices are helpful because they determine the accuracy of each model used. Basically, they’re a summary of prediction results on your classification problem. The output generated from your code will be a cool looking square: 

[(https://imgur.com/X6K6ZD7)]
Random Forest confusion matrix

For instance, this above confusion matrix was generated for my Random Forest model, which performed the highest in terms of accurately predicting red and white wine.  The way to interpret this is simple (although it looks very complex).  You count all the values in each square (mine totaled 1300). I’m interested in the percentage of the truly accurate predictions of red and white wines / the total count. So that would be the values in the darkest blue squares (958 + 334 /1300 = 0.99). If you multiply 0.99 x 100, this would generate 99%. So, my confusion matrix for Random Forest showed an accuracy of 99%. For the remaining models, my confusion matrices showed accuracies of:

* K-Nearest Neighbors (kNN): 94%

* Logistic Regression: 98%

* SVM: 94%

* Decision Tree: 96%

Lastly wrapping up my predictive modeling, I used deep learning to predict red or white wine accurately.  I decided to use Keras for modeling my data. Keras contains numerous implementations of commonly used neural network building blocks such as layers, objectives, activation functions, optimizations, and a host of tools to make working with image and text data easier. Moreover, Keras is ideal for beginners, minimalistic, and its modular approach makes it easy to get deep neural networks up and running.  After setting up the training and testing data ( compiling the metrics, I ran the model. The final output showed the model had 99% accuracy.  So, it performed as well as the Random Forest machine learning model.


[(https://imgur.com/HDphYt6)]
Keras confusion matrix


In closing, the capstone project had a lot of components that were very telling.  The EDA showed a lot of strong relationships between the wine type features.  Our statistical analyses of red and white wines revealed positive correlations.  We also saw that Random Forest and Keras models had the highest level of accuracy in predicting whether a wine was red or white.  While these are great results, there are some drawbacks.  Since the red wine and white wines were so imbalanced, I suspect that this might have affected the predictive modeling.  It would be helpful to have a more balanced dataset.  Also, while Keras performed very well, I would like to dabble in changing some parameters to see if that would affect accuracy.  Also, if there are any other features to this dataset, which would make it more robust, I would like to test that out to see if it would affect the results of our predictive models.  Overall, I really enjoyed analyzing such a fun dataset for my last project at Flatiron School.  I hope to use these skills, and the countless others I learned in the data science program to many more projects as I progress in this career.

