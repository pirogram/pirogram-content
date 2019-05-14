title: Boxplot
--- |
  Boxplot is another type of Statistical plot which helps with visualizing the `Statistical summary` of the data. Boxplot makes a `box` and `whisker`, the box extends from the lower to upper quartile values of the data, with a line at the `median`. The whiskers extend from the box to show the range of the data.
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
  Violin plots are similar to box plots but they add useful information such as the `distribution` of the data. Box plots show data points outside 1.5 * the inter-quartile range (IQR) as outliers above or below the whiskers whereas violin plots show the `whole range` of the data.
  Violin plot returns `bodies` which is a list of the matplotlib.collections.PolyCollection instances containing the filled area of each violin. The plot can be customized by re-setting the keyword arguments like `edgecolors`, `facecolor`, `linewidths`, `antialiaseds`, `offsets` which have default setting of None.
---
type: live-code
id: d2a916c3-4412-4082-aca0-4243e7cb67d6
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  fig, ax = plt.subplots()
  ax.violinplot(iris.iloc[:, :4].values)
  ax.set_title('Violinplot of iris dataset columns')
  ax.set_ylabel('Length in cm')
  ax.set_xticks(np.arange(1,5))
  ax.set_xticklabels(iris.iloc[:, :4].columns)
  plt.show()
---
