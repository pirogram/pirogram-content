title: Statistical Plots
--- |
  The Statistical plots like boxplot, violinplot and histogram help with visualizing the `Statistical summary` and `distribution` of the data. Boxplot makes a `box` and `whisker`, the box extends from the lower to upper quartile values of the data, with a line at the median. The whiskers extend from the box to show the range of the data.
---
type: live-code
id: ae8c4f5f-7e5c-4e4b-bed3-fd680bfb7fa7
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  iris = pd.read_csv('data/iris.csv')
  # Select numeric columns for creating boxplot
  data = iris.iloc[:, :4].values
  labels = iris.iloc[:, :4].columns.tolist()

  # Create boxplot with parameter patch_artist = True to add fill color
  fig, ax = plt.subplots(figsize = (9,5))
  ax.boxplot(data, labels = labels, patch_artist=True)
  ax.set_title('Boxplot of iris dataset columns')
  ax.set_ylabel('Length in cm')

  plt.show()
--- |
  Histograms are used to visualize the `distribution` of a quantitative variable. The values are placed into different bins and the frequency of observations in each of those bins is calculated. The data is considered to be normally distributed when the curve is symmetrical around mean and skewed if the mean is on either side of the peak but not at the peak. Here are the histograms of iris numeric columns on a figure with 2 rows and 2 cols.
---
type: live-code
id: c9d7dbfa-20c9-4d9f-8aa6-9001c3b54162
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  fig = plt.figure(figsize = (9,7))

  plt.subplot(221)
  plt.hist(iris['sepal_length'].values)
  plt.xlabel('Sepal Length in cm')
  plt.ylabel('Frequency')


  fig.suptitle('Histogram of numeric columns of iris dataset')
  plt.subplot(222)
  plt.hist(iris['sepal_width'].values)
  plt.xlabel('Sepal Width in cm')

  plt.subplot(223)
  plt.hist(iris['petal_length'].values)
  plt.xlabel('Petal Length in cm')
  plt.ylabel('Frequency')


  plt.subplot(224)
  plt.hist(iris['petal_width'].values)
  plt.xlabel('Petal Width in cm')


  plt.show()
--- |
  Violin plots are similar to box plots but they add useful information such as the `distribution` of the data. Box plots show data points outside 1.5 * the inter-quartile range (IQR) as outliers above or below the whiskers whereas violin plots show the `whole range` of the data.
  Violin plot returns `bodies` which is a list of the matplotlib.collections.PolyCollection instances containing the filled area of each violin. The plot can be customized by re-setting the keyword arguments like `edgecolors`, `facecolor`, `linewidths`, `antialiaseds`, `offsets` which have default setting of None.
---
type: live-code
id: d2a916c3-4412-4082-aca0-4243e7cb67d6
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  iris = pd.read_csv('data/iris.csv')
  violin_plot = plt.violinplot(iris.iloc[:, :4].values);
  for pc in violin_plot['bodies']:
    pc.set_facecolor('red')
    pc.set_edgecolor('black')
    pc.set_alpha(1)
  plt.title('Violinplot of iris dataset columns')
  plt.ylabel('Length in cm')
  plt.xticks(np.arange(1,5), iris.iloc[:, :4].columns)
  plt.show()
---
