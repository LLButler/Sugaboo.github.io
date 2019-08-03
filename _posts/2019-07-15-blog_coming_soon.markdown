---
layout: post
title:      "Breast cancer predictions with Machine and Deep learning"
date:       2019-07-15 23:29:58 -0400
permalink:  blog_coming_soon
---


Another challenging project is done [insert applause and cheers].  This time we were had to use deep learning models and apply that methodology to a problem.  This task was hard (at least for me) because deep learning is so complex.  

So, you might be asking what is deep learning?  Deep learning as I mentioned earlier is quite complex and is a subset of machine learning.  Machine learning uses algorithms that parse, learn and apply data to make informs decisions.   Basically, machine learning makes the algorithm capable of performing a function with the data given to it, and gets progressively better at that function.  Deep learning is a subset of machine learning, but the capabilities are different.  If a machine learning algorithm returns an inaccurate prediction, then the programmer needs to step in and make adjustments. But with a deep learning model, the algorithms can determine on their own if a prediction is accurate or not.

A deep learning model is designed to continually analyze data with a logic structure similar to how a human would draw conclusions. To achieve this, deep learning uses a layered structure of algorithms called an artificial neural network (ANN). The design of an ANN is inspired by the biological neural network of the human brain. This makes for machine intelligence that’s far more capable than that of standard machine learning models.  So deep learning structures algorithms in layers to create an “artificial neural network” that can learn and make intelligent decisions on its own.

Now that the definition of deep learning is out the way, let us get back to the module 4 project.  I decided to compare machine learning models to a deep learning model for my project.  I choose to look at breast cancer data, which was obtained from the University of California, Irvine.  This data set originated in the early 1990s when Dr. William H. Wolberg was curious if he could find a way to accurately predict breast cancer diagnosis based using fine needle aspirations (FNA) obtained from a breast mass.  FNA were performed on 569 patients and then stained to help differentiate distinguished cell nuclei.  Samples were classified as cancer-based (i.e. – malignant) through biopsy and historical confirmation. Non-cancer samples (i.e. – benign) were confirmed by biopsy or follow ups.  My problem statement for this project was to determine which machine learning model or deep learning model could most accurately detect malignant breast cancer.

My initial start (as with all projects) was to load the necessary libraries and data.  I look at the dataset using` .head()` and `.tail()`, as well as analyzing the shape of the data.  Again, there were 569 rows of data, which corresponded to each individual patient.  Additionally, there were 33 columns or features to the data (such as ID, diagnosis, and details about the FNA masses).  There was a completely useless column called Unnamed 32, which had nothing but null values.  This was dropped from the dataset, so it wouldn’t skew the analyses.  I also noticed that the ID column was comprised of integer values.  Since this column was just full of patient ID numbers, it wouldn’t be included in my analyses either.

So, once I took a quick look at the data and addressed the missing values, I moved on to the exploratory data analysis (EDA).  EDA probably is my most favorite aspect of working with data, since I love visualizing data.  I checked the summary stats using `.describe()` to get a feel for the data.  I didn’t see any data points that would skew my results.  Analyzing the histograms of the masses showed the distribution, but nothing really stood out.  I checked a few scatter graphs looked at some of the mass features (area mean and symmetry worst) and I noticed many of the masses were clustered with a mean of 500 and symmetries between 0.2 to 0.3.  Since I am interested in the number of patients with either malignant or benign tumors, I made a bar graph to visualize this.  I saw out of the 569 patients, 212 had breast cancer malignancies and 357 had benign tumors.  

Next step was to transform the malignant and benign columns, which were categorical values.  Categorical values can not be analyzed properly in the machine and deep learning models, so changing them to 1 and 0 (i.e. – malignant or benign) was the next step.  I did run another scatter plot of all the columns against the diagnosis column to see if anything stood out.  This generated a massage scatter plot of all the features, so I scaled it down.  What stood out mainly for me visually was the malignant tumors were much larger in terms of perimeter, area, radius than the benign ones.  Also, the malignant tumors generally had more texture to them.  Then I generated a correlation table and heat map to look at all the features.  I ran it out of curiosity to see if any other features were worth examining.  I didn’t see anything else and furthermore, for this project, I was interested in predictive modeling looking at the breast cancer diagnosis.    

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/hr_histogram_plots.png)]

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/mod%204%20scatter%20plot.png)]

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/mod%204%20tumor%20types.png)]

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/mod%204%20tumor%20scatter%20plot.png)]


I needed to prep my data for predictive modeling by splitting it into training and testing data.  Again, I was solely interested in which models would best predict breast cancer malignancy.  My independent data will tell me the features that can detect if a patient has cancer, and my dependent data will tell me if a patient has cancer or not.  I decided to use an 80% training set and 20% testing set. Next using the StandardScaler feature in Sklearn, I scaled the data.  Scaling the data brings all features to the same level of magnitude.  So, the data will be within a specific range for example 0 -100 or 0 – 1.  

I first looked at the machine learning models and generated the model testing accuracy.  The output was: 

* K Nearest Neighbor: 94%
* Logistic regression: 97%
* Support Vector Machine: 95%
* Decision Tree: 94% 
* Random Forest: 96%

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/CM_KNN.PNG)]

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/CM_log%20reg.PNG)]

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/CM_SVM.PNG)]

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/CM_DT.PNG)]

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/CM_RF.PNG)]

So, it seemed as though Logistic Regression performed the best out of all the models.  A close second was Random Forest at 96%.  As I moved on the deep learning, I decided to use Keras for modeling my data.  Keras contains numerous implementations of commonly used neural network building blocks such as layers, objectives, activation functions, optimizations, and a host of tools to make working with image and text data easier.  What I like about Keras is it’s great for beginners, minimalistic, and its modular approach makes it easy to get deep neural networks up and running.  

I loaded the necessary libraries to run Keras, as well as a few libraries from Sklearn for the deep learning/neural network.  I needed to add layers to the neural network, so I did that.  Also adding dropout to the model prevents overfitting of the data.  After compiling the metrics, I ran the model.  The final output showed the model had 95% accuracy.  So that’s not too bad, the deep learning model was very accurate in predicting breast cancer malignancies.  

![(https://github.com/Sugaboo/dsc-4-final-project-online-ds-pt-112618/blob/master/CM_Keras.PNG)]

In closing, the machine learning models with the highest level of accuracy in predicting malignancies was logistic regression at 97%.  Random Forest was a close second, coming in at 95%. The deep learning model using Keras showed 95%, as well as SVM.

I was hoping that the neural network would show the highest level of accuracy (since it mimics the human brain), but its performance was on par in comparison to some of the machine learning models.  Overall that still not bad though.  While using machine learning or deep learning models can help predict which patients have breast cancer, this technique is still fallible.  Even using a medical doctor to determine breast cancer is not 100% accurate.  However, this technique does show great promise.  

I believe using either machine learning or deep learning to predict breast cancer, along with the skillful trained eye of a physician, will be the best course of action for assessing breast cancer malignancies in patients. This methodology can help minimize false negatives (which would subject the patient to unecessary testing) and maximize true positives in breast cancer.  

