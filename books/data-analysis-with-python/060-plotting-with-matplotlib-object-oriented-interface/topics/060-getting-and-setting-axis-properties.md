title: Getting and Setting axis properties
--- |
  ### Axes limits
  The `limits` of x and y axis are inferred by matplotlib based on the range data at X and Y axis. A convenient method to `get` or `set` axis properties is [Axes.axis](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.axis.html#matplotlib.axes.Axes.axis). It returns the axis limits in the order xmin, xmax, ymin, ymax. Either none or all of the limits must be given.
---  
type: live-code
id: 9171d585-f22d-4eef-873f-f24cd856fa94
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(5)
  y = x ** 2
  fig, ax = plt.subplots()
  ax.plot(x, y, 'bo')
  print('Current axis limits',ax.axis())
  # Reset the limits
  ax.axis([-1, 5, -1, 20])
  plt.show()
--- |
  You can `get` and `set` only x or y limits using [Axes.get_xlim](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.get_xlim.html#matplotlib-axes-axes-get-xlim) or [Axes.set_xlim](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set_xlim.html#matplotlib.axes.Axes.set_xlim) respectively. Conversely, use [Axes.get_ylim](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.get_ylim.html#matplotlib-axes-axes-get-ylim) and [Axes.set_ylim](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set_ylim.html#matplotlib.axes.Axes.set_ylim) to `get` and `set` Y limits.
---
type: live-code
id: 8acc525b-9338-41c2-ab7f-ac66cfab300e
code: |
  type: live-code
  id: 54f50c98-9718-405f-ba2e-485e47d2fa5a
  code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(-5, 6)
  y = x ** 3
  fig, ax = plt.subplots()

  ax.plot(x, y, 'bo')
  print('Default xlim: ',ax.get_xlim())
  ax.set_xlim([-8,8])
  ax.grid(True)
  plt.show()
---
type: live-code
id: 2a595a3a-18a8-4e93-977c-30e69cb4874a
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(-5, 6)
  y = x ** 3
  fig, ax = plt.subplots()

  ax.plot(x, y, 'bo')
  print('Default ylim: ',ax.get_ylim())
  ax.set_ylim([-150,150])
  ax.grid(True)
  plt.show()
--- |
  ### Axes ticks and tick labels
  Another important property of axis is the ticks. [Axes.get_xticks](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.get_xticks.html#matplotlib.axes.Axes.get_xticks) and [Axes.get_yticks](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.get_yticks.html#matplotlib.axes.Axes.get_yticks) return the x and y ticks as a list of locations. Whereas we can set the x and y ticks by passing a list of ticks to [Axes.set_xticks](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set_xticks.html#matplotlib.axes.Axes.set_xticks) and [Axes.set_yticks](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set_yticks.html#matplotlib.axes.Axes.set_yticks). The x and y tick labels can be accessed using [get_xticklabels] (https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.get_xticklabels.html#matplotlib.axes.Axes.get_xticklabels), [Axes.get_yticklabels](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.get_yticklabels.html#matplotlib.axes.Axes.get_yticklabels) and set using [set_xticklabels] (https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set_xticklabels.html#matplotlib.axes.Axes.set_xticklabels), [Axes.set_yticklabels]  (https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set_yticklabels.html#matplotlib.axes.Axes.set_yticklabels).
---
type: live-code
id: c7b79b65-9d11-4383-8653-784fc06ae0f8
code: |
  import numpy as np
  import matplotlib.pyplot as plt

  x = np.arange(5)
  y = x ** 2
  fig, ax = plt.subplots()
  ax.plot(x, y, '*', markersize = 9)

  print('Default xticks: ', ax.get_xticks())
  print('Default yticks: ', ax.get_yticks())

  # Pass the data points a x and y ticks
  ax.set_xticks(x)
  ax.set_yticks(y)

  # Set the ticklabels by passing
  ax.set_xticklabels(['zero', 'one', 'two', 'three', 'four'])
  ax.set_yticklabels(['zero', 'one', 'four', 'nine', 'twenty five'])

  plt.show()
---
