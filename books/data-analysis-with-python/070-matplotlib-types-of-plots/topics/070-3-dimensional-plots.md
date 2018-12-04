title: 3 dimensional Plots
--- |
  Matplotlib supports 3-dimensional plots using Toolkits, collections of application-specific functions that extend Matplotlib. We will be using [mplot3d](https://matplotlib.org/mpl_toolkits/mplot3d/index.html#mplot3d) from mpl_toolkits. We start by creating a new [matplotlib.figure.Figure](https://matplotlib.org/api/figure_api.html#matplotlib.figure.Figure) and add a new axes using a `3d projection`.
---
type: live-code
id: 8377a5ca-3b98-47ec-afcf-b0e60f25367c
code: |
  import matplotlib.pyplot as plt
  from mpl_toolkits.mplot3d import Axes3D
  fig = plt.figure()
  ax = fig.add_subplot(111, projection='3d')
  plt.show()
--- |
  ### Line plot
  we can plot different types of 3 dimensional plot on a figure with 3-dimensional axes created above. Here is an example of 3-d lineplot from the data used earlier.
---
type: live-code
id: 7f69edd4-c16e-4d48-84bd-f6f65eabdf1d
code: |
  import matplotlib.pyplot as plt
  from mpl_toolkits.mplot3d import Axes3D
  import numpy as np

  fig = plt.figure()
  ax = fig.gca(projection='3d')

  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  z = np.cos(x)

  ax.plot(x, y, z)
  plt.show()
--- |
  ### Scatter plot
  Here is the 3-D scatterplot of iris dataset using parameters s(size in points^2) and c(color).
---
type: live-code
id: 41173cb6-9c1d-414d-a82d-3aca3e6480fc
code: |
  import matplotlib.pyplot as plt
  from mpl_toolkits.mplot3d import Axes3D
  import pandas as pd
  import numpy as np

  iris = pd.read_csv('data/iris.csv')
  fig = plt.figure()
  ax = fig.gca(projection='3d')

  x = iris['sepal_length']
  y = iris['sepal_width']
  z = iris['petal_length']

  ax.scatter3D(x, y, z, c = x, s = 50)
  plt.show()
--- |
  ### Surface plots:
  Surface plots show relationship between dependent variable and two independent variables. The independent variables are in the form of two-dimensional regular grids and the dependent variable is evaluated at each point.
---
type: live-code
id: 4e8c7c09-c5f6-428f-a82f-9fc257022cfd
code: |
  import matplotlib.pyplot as plt
  from mpl_toolkits.mplot3d import Axes3D
  import numpy as np

  fig = plt.figure()
  ax = fig.gca(projection='3d')

  X = np.arange(-5, 5, 0.25)
  Y = np.arange(-5, 5, 0.25)
  X, Y = np.meshgrid(X, Y)
  R = np.sqrt(X**2 + Y**2)
  Z = np.sin(R)

  ax.plot_surface(X, Y, Z, rstride=1, cstride=1, cmap='coolwarm')
  plt.show()
--- |
  ### 3-D Contour plot
  Contour plot are used to represent 3 dimensional surface by plotting constant slices, called contours, on a 2-dimensional format. Matplotlib also supports a 3 dimensional contour plot.
---
type: live-code
id: 29c1121c-972c-4ec6-b085-9a44e3932ed8
code: |
  import matplotlib.pyplot as plt
  from mpl_toolkits.mplot3d import Axes3D
  import numpy as np

  fig = plt.figure()
  ax = fig.gca(projection='3d')
  X = np.arange(-5, 5, 0.25)
  Y = np.arange(-5, 5, 0.25)
  X, Y = np.meshgrid(X, Y)
  R = np.sqrt(X**2 + Y**2)
  Z = np.sin(R)
  ax.contour(X, Y, Z, cmap='coolwarm')
  plt.show()
---
