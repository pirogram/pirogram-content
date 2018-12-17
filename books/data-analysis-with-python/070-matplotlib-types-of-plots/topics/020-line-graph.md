title: Line graph
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
  print(dates[:5])
  # Create an array of random numbers
  values = np.random.randn(100)
  print(values[:5])

  fig, ax = plt.subplots(figsize = (10,5))
  ax.plot(dates, values)
  ax.set_title('line plot')
  ax.set_xlabel('Dates')
  ax.set_ylabel('Values')
  plt.show()
---
type: testless-coding-question
id: ad76e7eb-c7dd-43be-ad55-3fa0d9d8fad8
question: |
  Create a line graph of the stock price of `Apple` and `Facebook` from the [timeseries](/data/matplotlib/timeseries.csv) dataframe given below. Add a legend to indicate each ticker with a distinct color. The figure should looks like this:
  ![Lineplot](assets/img/lineplot.png)
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  import pandas as pd

  ts = pd.read_csv('data/timeseries.csv')
  # Your code goes here.
---
