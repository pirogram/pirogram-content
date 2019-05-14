title: Histogram
--- |
  Histogram is a type of Statistical plot which helps visualizing the `distribution` of the quantitative variables.
  It is created by binning a range of values (dividing the values into intervals) and counting the frequency of observations in each of those bins.

  The data is considered to be `normally distributed` when the curve is symmetrical around mean and `skewed` if the mean is on either side of the peak but not at the peak. Here are the histograms of all the numeric columns in [Iris dataset](/data/matplotlib/iris.csv) on a figure with 2 rows and 2 cols.
---
type: live-code
id: c9d7dbfa-20c9-4d9f-8aa6-9001c3b54162
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np
  iris = pd.read_csv('/data/matplotlib/iris.csv')

  fig, ((ax1, ax2), (ax3, ax4)) = plt.subplots(2, 2, figsize = (9,7))

  ax1.hist(iris['sepal_length'].values)
  ax1.set_xlabel('Sepal Length in cm')
  ax1.set_ylabel('Frequency')

  ax2.hist(iris['sepal_width'].values)
  ax2.set_xlabel('Sepal Width in cm')

  ax3.hist(iris['petal_length'].values)
  ax3.set_xlabel('Petal Length in cm')
  ax3.set_ylabel('Frequency')

  ax4.hist(iris['petal_width'].values)
  ax4.set_xlabel('Petal Width in cm')
  fig.suptitle('Histogram of numeric columns of iris dataset')
  plt.show()
---
