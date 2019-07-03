---
layout: post
title:      "Bar Plots in Python"
date:       2019-07-03 05:39:23 -0400
permalink:  bar_plots_in_python
---


I feel data visualization is a major crux of a Data Scientist job.  For every project, an Exploratory Data Analysis (EDA) is required.  EDA is extremely helpful as it gives you an insight into your data and makes it easier to understand the dataset your analyzing.  EDA is also critical to share with your clients, manager and whomever else you’re presenting your data to.  Overall, EDA provides a very clear and concise visual understanding of the data.  Most people like visualizing data versus reading boring charts and tables. 

What’s lovely about Python is that is has a multitude of visualization libraries.  In our Data Science program, we use Matplotlib and Seaborn mostly.  Matplotlib is a multi-platform data visualization library built on NumPy arrays and designed to work with the broader SciPy stack.  One of Matplotlib’s most important features is its ability to play well with many operating systems and graphics backends.  Seaborn is a Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics.  Seaborn also address two frustrations Matplotlib users have: frustrations with Matplotlib parameters and the fact that working with DataFrames doesn’t go quite as smoothly with Matplotlib (which can be annoying if you’re doing exploratory analysis with Pandas).  This nice thing is once you’re proficient in Matplotlib, you essentially are proficient in using Seaborn.

Now that the overview of the two is out the way, the visualization capacity of both are extremely useful.  Since we need to focus on a visualization technique of my choice for this blog, I’m going to focus on Bar Plots, which can be done in both libraries (insert cheers and applause).  So, you’re probably asking why are Bar Plots important?  I’m glad you asked!  Bar plots are highly effective when visualizing categorical data with less than or equal to 10 categories.  Bar Plots are ideal for categorical data because you’re able to see the difference between the size of the bar (i.e. magnitude); categories are also easily divided, and color coded too. There are 3 different types of bar plots: regular, grouped, and stacked.  Regular bar plots there really is nothing fancy, its just a regular bar plot.  Grouped bar plots allow us to compare multiple categorical variables.  Lastly, Stacked bar plots are great for visualizing the categorical make-up of different variables.

* Regular Bar Plot: [https://cdn-images-1.medium.com/max/800/1*KH2IUzjWtvv5vE16MmUqkA.png]

* Grouped Bar Plot: [https://cdn-images-1.medium.com/max/800/1*eFUevHu9wMgnwSlcOSnSFw.png]

* Stacked Bar Plot: [https://cdn-images-1.medium.com/max/800/1*XS1QXGy8CzIPYrrC7bFFEA.png]

There are also some variations of the Bar Plot: lollipop plot and circular.  The lollipop plot replaces the bars with a segment and a dot. It results in a less cluttered figure that is often more attractive.  The circulation bar plot is great for many groups but is less accurate and ideal if you have a pattern to the dataset. 

* Lollipop Bar Plot: [https://www.data-to-viz.com/graph/barplot_files/figure-html/unnamed-chunk-4-1.png
]
* Circulation Bar Plot: [https://www.data-to-viz.com/graph/barplot_files/figure-html/unnamed-chunk-5-1.png]

So, what are the advantages of Bar Plots?  They are easy to interpret, show a clear relation between size/comparison, and present either large or small values quite well.  What are the disadvantages of using Bar Plots?  Another great question.  Bar plots often require additional explanation, they fail to expose key assumptions/causes/impacts/patterns and they are easily manipulated to give false impressions.  

Regardless of whichever type of data visualization you decided to use, Python has the capacity to plot and analyze many different types of data with a huge array of methods.  This blog just covers a single type of visualization, which is the tip of the iceberg.  What would be ideal and the best for your Python learning and understanding would be exploring both the Matplotlib and Seaborn libraries to determine which will be the best for your data and what you're hoping to accomplish.

*Sources*: 
[https://jakevdp.github.io/PythonDataScienceHandbook/04.00-introduction-to-matplotlib.html]

[https://www.datacamp.com/community/tutorials/seaborn-python-tutorial]

[https://www.kdnuggets.com/2018/07/5-quick-easy-data-visualizations-python-code.html]

[https://www.data-to-viz.com/graph/barplot.html]


