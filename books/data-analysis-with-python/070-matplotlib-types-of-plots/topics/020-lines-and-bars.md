title: Lines and Bars
--- |
  The default plotting style in matplotlib is a line graph and both axes.plot and pyplot.plot return a `line graph`. Line plots are most commonly used to plot continuous data, `Timeseries` plot is a common example.
---
type: live-code
id: 6db1e8c5-7cfb-4bd4-b3d3-a47f6f97dee3
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  import pandas as pd

  today = np.datetime64('today')
  # Create an array of dates over last 100 days
  dates = pd.date_range(end = today, periods=100)
  # Create an array of random numbers
  values = np.random.randn(100)

  fig, ax = plt.subplots(figsize = (10,5))
  ax.plot(dates, values)
  ax.set_title('line plot')
  ax.set_xlabel('Dates')
  ax.set_ylabel('Values')
  plt.show()
--- |
  Bar graphs are used more commonly to represent discreet values. Here is a bar graph of `count` of movies by `ratings` in year 2016 from [Imdb dataset](/data/movie_metadata.csv).
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
  # Create bar graph of width 0.6.
  plt.bar(movie_ratings_2016.index, movie_ratings_2016, width=0.6)

  # Set labels and title
  plt.xlabel('Movie Ratings')
  plt.ylabel('Count')
  plt.title('Count of movies with different ratings in 2016')
  plt.show()
--- |
  To represent discreet value of multiple variables by a category, we create `grouped bar chart`. Here is a plot of `mean` values by species in iris dataset. We plot the `species` vs the `mean` for each variable on the `same axes` but move the `location` of `xtick` so that the bars do not overlap.
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
  Grouped bars can be `stacked` using the parameter `bottom` to ensure that the next bar in the group is stacked on the top of the previous in the same group.
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
id: ad76e7eb-c7dd-43be-ad55-3fa0d9d8fad8
question: |
  Create a line graph of the stock price of `Apple` and `Facebook` from the `timeseries` dataframe given below. Add a legend to indicate each ticker with a distinct color. The figure should looks like this:
  ![Lineplot](assets/img/lineplot.png)
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  import pandas as pd

  ts = pd.read_csv('data/timeseries.csv')
  # Your code goes here.
---
