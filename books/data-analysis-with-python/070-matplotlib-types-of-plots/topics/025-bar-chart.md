title: Bar chart
--- |
  Bar graphs are used more commonly to represent discrete values. Here is a bar graph of `count` of movies by `ratings` in year 2016 from [Imdb dataset](/data/matplotlib/imdb.csv).
---
type: live-code
id: 3bf2211f-0b1e-438c-8c09-98554805553d
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  imdb = pd.read_csv('data/matplotlib/imdb.csv')

  # Find count of movies by ratings and store in x and y values.
  movie_ratings_2016 = imdb[imdb.title_year == 2016].content_rating.value_counts()
  # Create bar graph of width 0.6.
  plt.bar(movie_ratings_2016.index, movie_ratings_2016, width=0.6)

  # Set labels and title
  plt.xlabel('Movie Ratings')
  plt.ylabel('Count')
  plt.title('Count of movies with different ratings in 2016')
  plt.show()
--- |
  To represent discrete value of multiple variables by a category, we create `grouped bar chart`. Here is a plot of `mean` values by species in [Iris dataset](/data/matplotlib/iris.csv). We plot the `species` vs the `mean` for each variable on the `same axes` but move the `location` of `xtick` so that the bars do not overlap.
  * Set the parameter barwidth to use in plot.
  * Create an array of X values (number of unique species in the dataset)
  * Plot X vs the variables in iris dataset, increment the X value by the barwidth at each call so that the bars align.
  * Set xticks location to the array of X values.
  * Set xticks labels to names of the species.
---
type: live-code
id: a7023926-b4ff-4cea-a7bb-96976bf1cd1a
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  import pandas as pd

  iris = pd.read_csv('data/matplotlib/iris.csv')
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
  Grouped bars can be `stacked` using the parameter `bottom` to ensure that the next bar in the group is stacked on the top of the previous in the same group.
---
type: live-code
id: db335ba2-ada3-43fe-b884-42e135cb86d6
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  import pandas as pd

  iris = pd.read_csv('data/matplotlib/iris.csv')
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

  # Call bar() with parameter `bottom` to set the bottom of the bar at the top of previous bar.
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
type: testless-coding-question
id: d7fe319f-57d6-4c9d-ae21-6ecb4f00e443
question: |
  Create a barchart of stock price of Facebook vs apple in the year 2017. The filtered dataframe is created using the code below. The chart should look like this:
  ![Barchart](assets/img/stocks_barchart.png)
code: |
  import numpy as np
  import pandas as pd
  import matplotlib.pyplot as plot

  ts.index = pd.to_datetime(ts.index)
  ts = ts[ts.index.year == 2017]
  ts_2017 = ts.groupby([ts.index.year.rename('year'),ts.index.month.rename('month')])['AAPL', 'FB'].last()
  ts_2017.index = ts_2017.index.droplevel(0)
  # Your code goes here
---
