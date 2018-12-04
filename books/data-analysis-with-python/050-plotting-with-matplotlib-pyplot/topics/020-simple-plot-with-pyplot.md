title: Simple plot with Pyplot
--- |
  This section is about how to use [matplotlib.pyplot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.html) to create various plots and customize them.

  Maplotlib supports different data types like `python lists`, `numpy arrays` as well as a `pandas series` as data sources but internally all the sequences are converted to numpy arrays. We will make generous use of numpy for array creation and Pandas for reading, slicing and grouping data. If you are unfamiliar with Numpy, we highly recommend that you first check out our book on [Numpy array basics](). Lets create our first plot using [pyplot.plot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.plot.html#matplotlib.pyplot.plot) from numpy arrays.

  When pyplot plot command is called without any formatting parameters, pyplot uses the following defaults:
  * Figure size: 6.4 X 4.8 inches
  * Plot style: solid line
  * Linewidth: 1.5
  * Color: Blue (code 'b', hex code: '#1f77b4')

  Do not forget to use `plt.show()` to display the figure.
---
type: live-code
id: d25767c4-b7d4-4e31-a239-a1e688addad4
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(5)
  y = x ** 2
  plt.plot(x,y)
  plt.show()
--- |
  When you pass only one set of arrays as data to pyplot plot, matplotlib assumes it is a sequence of y values, and automatically generates the x values for you. In the example below, the data is an array of random numbers. The x axis values are inferred as the range(len(x)).
---
type: live-code
id: 8189be4c-362e-4341-93c2-6858305700b9
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.array([10,5,21,9])
  plt.plot(x)
  plt.show()
---
