title: Lines and Bars
--- |
  The default plotting style in matplotlib is a line graph and both axes.plot and pyplot.plot return a `line graph`. Line plots are most commonly used to plot continuous data, Timeseries plot is a common example.
---
type: live-code
id: 6db1e8c5-7cfb-4bd4-b3d3-a47f6f97dee3
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  import pandas as pd
  today = np.datetime64('today')
  dates = pd.date_range(end = today, periods=100)
  values = np.random.randn(100)
  fig = plt.figure(figsize = (10,5))
  plt.plot(dates, values)
  plt.title('line plot')
  plt.xlabel('Dates')
  plt.ylabel('Values')
  plt.show()
--- |
  Bar graphs are used more commonly to represent discreet values. Here is a bar graph of count of movies by ratings in year 2016 from `imdb` dataset.
---
type: live-code
id: 3bf2211f-0b1e-438c-8c09-98554805553d
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  imdb = pd.read_csv('data/movie_metadata.csv')

  # Find count of movies by ratings and store in x and y values.
  movie_ratings_2016 = imdb[imdb.title_year == 2016].content_rating.value_counts()
  x = movie_ratings_2016.index
  y = movie_ratings_2016.values

  # Create bar graph of width 0.6.
  plt.bar(x, y, width=0.6)

  # Align xlim and xticks
  #plt.xlim(plt.xlim()[0] - 0.5, plt.xlim()[-1] + 0.5)

  # Set labels and title
  plt.xlabel('Movie Ratings')
  plt.ylabel('Count')
  plt.title('Count of movies with different ratings in 2016')

  plt.show()
--- |
  Bar graphs can be created with grouped bars on each xlabel. Here is a grouped Bar chart of `mean` values by species in `iris` dataset.
---
type: live-code
id: a7023926-b4ff-4cea-a7bb-96976bf1cd1a
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  import pandas as pd

  iris = pd.read_csv('data/iris.csv')

  # Find mean values by species
  iris_mean = iris.groupby('species').mean()

  # Create figure, axes
  fig, ax = plt.subplots(figsize = (8,5))

  # Set bar width
  bar_width = 0.20
  index = np.arange(iris_mean.index.nunique())

  # Call bar() with `data` and appropriate `label`.
  ax.bar(index, iris_mean['sepal_length'], bar_width, label = 'sepal length')
  ax.bar(index + bar_width, iris_mean['sepal_width'], bar_width, label = 'sepal width')
  ax.bar(index + 2*bar_width, iris_mean['petal_length'], bar_width, label = 'petal length')
  ax.bar(index + 3*bar_width, iris_mean['petal_width'], bar_width, label = 'petal width')

  # Add labels, titles, legend and set ticks
  ax.set_title('Mean values of iris data by species')
  ax.set_xlabel('Species')
  ax.set_xticks(index + bar_width / 2)
  ax.set_xticklabels(iris_mean.index.tolist())
  ax.set_ylabel('Mean')
  ax.legend()

  plt.show()
--- |
  Grouped bars can be stacked using the parameter bottom to ensure that the next bar in the group is stacked on the top of the previous in the same group.
---
type: live-code
id: db335ba2-ada3-43fe-b884-42e135cb86d6
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  import pandas as pd

  iris = pd.read_csv('data/iris.csv')

  # Find mean values by species
  iris_mean = iris.groupby('species').mean()

  # Create figure, axes
  fig, ax = plt.subplots(figsize = (9,5))

  # Set bar width
  bar_width = 0.3
  index = np.arange(iris_mean.index.nunique() )

  sepal_length = iris_mean['sepal_length'].values
  sepal_width = iris_mean['sepal_width'].values
  petal_length = iris_mean['petal_length'].values
  petal_width = iris_mean['petal_width'].values

  # Call bar() with parameter bottom to ensure stacked bars.
  ax.bar(index + 0.1, sepal_length, bar_width,label = 'sepal length')
  ax.bar(index + 0.1, sepal_width, bar_width,label = 'sepal width', bottom = sepal_length)
  ax.bar(index + 0.1, petal_length, bar_width,label = 'petal length', bottom = sepal_length + sepal_width)
  ax.bar(index + 0.1, petal_width, bar_width,label = 'petal width', bottom = sepal_length + sepal_width+ petal_length)

  # Add labels, titles, legend and set ticks
  ax.set_title('Mean values of iris data by species')
  ax.set_xlabel('Species')
  ax.set_xticks(index + bar_width / 2)
  ax.set_xticklabels(iris_mean.index.tolist())
  ax.set_ylabel('Mean')
  ax.legend()

  plt.show()
---
