title: Simple Plot with Matplotlib
--- |
  Lets create a simple plot using  object oriented interface. We first create an instance of figure and axes in a single call using [pyplot.subplots](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplots.html#matplotlib.pyplot.subplots). The axes can be either a `single Axes object` or an `array of Axes objects` depending on the number of rows & columns specified during the subplots call.

  The main difference from the pyplot interface is that we plot on the specific `axes object` rather than relying pyplot to return the `current axes`.

  Matplotlib uses the following default parameters to create the plot:
  * Figure size: 6.4 X 4.8 inches
  * Plot style: solid line
  * Linewidth: 1.5
  * Color: Blue (code 'b', hex code: '#1f77b4')

  Do not forget to use `plt.show()` to display the figure.
---
type: live-code
id: a3d16472-9ac4-43a3-b13d-b8c33eac1bc2
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 11)
  y = x ** 2
  fig, ax = plt.subplots()
  ax.plot(x, y)
  plt.show()
--- |
  If a single list or array is passed to the plot() command, matplotlib assumes it is a sequence of `y values`, and automatically generates the x values. When we pass the array y from the earlier plot to ax.plot, it creates a similar plot with one exception - matplotlib `infers` the X axis values starting from 0.
---
type: live-code
id: 27eda68f-0968-444e-a9dd-743220da26c9
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  fig, ax = plt.subplots()
  ax.plot(y)
  plt.show()  
---
