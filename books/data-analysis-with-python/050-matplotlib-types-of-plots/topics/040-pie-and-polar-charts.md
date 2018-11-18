title: Pie and Polar charts
--- |
  Pie charts are most commonly used to show percentage or proportional data. They help in visualizing the percentage share of each category in the data. The graph is usually circular with each category in the form of a pie. Here is an example of a simple pie-chart of size of species in iris dateset.
---
type: live-code
id: e08c97dc-620b-449b-8563-df818a4c355b
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  iris = pd.read_csv('data/iris.csv')
  iris_size = iris.groupby('species').size()
  plt.pie(iris_size.values, labels = iris_size.index, autopct='%1.1f%%')
  plt.show()
--- |
  Pie chart can be generated for grouped data. Here is the pie chart of mean values in iris dataset by species.
---
type: live-code
id: 3343eee3-b465-4f2d-87d2-bee0de1b3b4d
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  iris = pd.read_csv('data/iris.csv')
  iris_mean = iris.groupby('species').mean()

  fig, axes = plt.subplots(nrows = 2, ncols = 2, figsize = (9,8))
  ax0, ax1, ax2, ax3 = axes.flatten()
  labels = iris_mean.index
  ax0.pie(iris_mean['sepal_length'].values, autopct='%1.1f%%')
  ax0.set_title('sepal length')

  ax1.pie(iris_mean['sepal_width'].values, autopct='%1.1f%%')
  ax1.set_title('sepal width')

  ax2.pie(iris_mean['petal_length'].values, autopct='%1.1f%%')
  ax2.set_title('petal length')

  ax3.pie(iris_mean['petal_width'].values, autopct='%1.1f%%')
  ax3.set_title('petal width')
  fig.legend(labels)
  plt.show()
---
