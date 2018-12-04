title: Getting and Setting axis properties
--- |
  ### Axes limits
  The limits of x and y axis are inferred by matplotlib based on the range data at X and Y axis. A convenient method to get or set axis properties is [matplotlib.pyplot.axis](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.axis.html#matplotlib.pyplot.axis). Here is an example of getting the axis properties.
---  
type: live-code
id: a7670c5b-25c4-4c8b-9465-b61d1a99077d
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(5)
  y = x ** 2
  plt.plot(x, y, 'bo')
  print(plt.axis())
  plt.show()
--- |
  We can also set the properties to a custom limits using [matplotlib.pyplot.axis](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.axis.html#matplotlib.pyplot.axis).
---
type: live-code
id: a440f070-edde-41bb-bcae-d5030ef92e68
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(5)
  y = x ** 2
  plt.plot(x, y, 'bo')
  plt.axis([-2, 8, -22, 25])
  plt.show()
--- |
  If you want to get or set only x or y limits, you can use [matplotlib.pyplot.xlim](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xlim.html#matplotlib.pyplot.xlim) or [matplotlib.pyplot.ylim](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.ylim.html#matplotlib.pyplot.ylim)
---
type: live-code
id: b712d557-bddb-4986-acb2-9dd1b44f235a
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(-5, 6)
  y = x ** 3
  plt.plot(x, y, 'bo')
  print('Default xlim: ',plt.xlim())
  plt.xlim([-8,8])
  plt.show()
---
type: live-code
id: d3c2032e-2f62-4f80-8eef-bcccd9abbadc
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(-5, 6)
  y = x ** 3
  plt.plot(x, y, 'bo')
  print('Default ylim: ',plt.ylim())
  plt.ylim([-50, 140])
  plt.show()
--- |
  ### Axes ticks and tick labels
  Another important property of axis is the ticks. We can use  [matplotlib.pyplot.xticks](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.xticks.html#matplotlib.pyplot.xticks) and [matplotlib.pyplot.yticks](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.yticks.html#matplotlib.pyplot.yticks) return the location and labels of the xticks and yticks respectively. Conversely, can set the ticks by passing ticks and labels to `xticks` or `yticks`.
---
type: live-code
id: 99589b17-734b-4179-b5f2-7b2084138e7f
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(5)
  y = x ** 2
  plt.plot(x, y, 'bo')
  print('Default xticks: ', plt.xticks())
  print('Default yticks: ', plt.yticks())
  plt.xticks(np.arange(5), ['zero', 'one', 'two', 'three', 'four'])
  plt.yticks(x**2, ['zero', 'one', 'four', 'nine', 'twenty five'])
  plt.show()
---
