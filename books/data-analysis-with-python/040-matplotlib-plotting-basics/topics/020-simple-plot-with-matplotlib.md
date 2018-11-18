title: Simple Plot with Matplotlib
--- |
  ### Plot using Object-oriented interface
  The most suitable data form for plotting using matplotlib is a numpy array. The command plot() returns a `line graph` by default. Given the arrays, we can plot their relationship using simple matplotlib commands as follows:
---
type: live-code
id: a3d16472-9ac4-43a3-b13d-b8c33eac1bc2
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  fig, ax = plt.subplots()
  ax.plot(x,y)
  plt.show()
--- |
  Note: If a single list or array is passed to the plot() command, matplotlib assumes it is a sequence of y values, and automatically generates the x values.
---
type: live-code
id: 27eda68f-0968-444e-a9dd-743220da26c9
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  fig, ax = plt.subplots()
  ax.plot(x)
  plt.show()  
--- |
  ### Plot using Pyplot interface
  Visualization with pyplot is very quick and efficient for a plot with single axes.
---
type: live-code
id: 0a218ca4-4b72-4ef6-8764-8d57ab25a3cc
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  plt.plot(x,y)
  plt.show()
---
