title: Plotting multiple data on same axes
--- |
  ### Object-oriented interface
  We can plot multiple sets of data on the same figure and axes by calling the `plot` function multiple times before the command plt.show(). For plots with multiple data on same axes, it becomes important to add a legend. [matplotlib.axes.Axes.legend](matplotlib.axes.Axes.legend) is used to add legend in object oriented approach. The default location of legend is 'best' for axes and 'upper right' for figures. It can be set to any other position using parameter `loc`.

---
type: live-code
id: daa3317d-816e-437a-9551-35c5c8a378ad
code: |
  import matplotlib.pyplot as plt
  import numpy as np

  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  z = np.cos(x)

  fig, ax = plt.subplots()
  ax.plot(x, y, color='b', linestyle = '--', label = 'Sin')
  ax.plot(x, z, color='r', linestyle = ':', label = 'Cos')

  # Set title
  ax.set_title('Sine and cos plot')

  # Add legend
  ax.legend()

  # Add gridlines
  ax.grid(linestyle='-', linewidth='0.5')

  plt.show()
--- |
  ### Pyplot interface
  Most functions in pyplot refer to an existing current `Figure` and current `Axes` or create a new one. The pyplot plot() gets the current Axes of the current Figure and then call its plot() method (it returns gca().plot()). Similarly plt.title() accesses the current axis and set_title() is a setter method that sets the title for that Axes object. Most other methods like plt.xlabel(), plt.xticks(), plt.grid(), plt.legend() work in similar way.

---
type: live-code
id: 7ecd26c7-b612-44df-a326-22a6cbf80071
code: |
  import matplotlib.pyplot as plt
  import numpy as np

  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  z = np.cos(x)

  plt.plot(x, y, 'b--', label = 'Sin')
  plt.plot(x, z, 'r^', label = 'Cos')

  #Add title
  plt.title('Sine and cos plot')

  # Add legend
  plt.legend()

  # Add gridlines
  plt.grid(True)


  plt.show()
---
