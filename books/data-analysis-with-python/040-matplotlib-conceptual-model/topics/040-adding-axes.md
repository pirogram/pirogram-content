title: Adding Axes
--- |
  ### Adding Axes using object-oriented interface
  Axes is the part of the figure with individual plots or graphs. One or more `axes` objects are added to `figure` to enable plotting. There are two ways of adding axes using stateless (object-oriented interface), [add_axes](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure.add_axes) or [add_subplot](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure.add_subplot). They both return a matplotlib.axes.Axes object.

    The call signature of add_axis is add_axis(rect) where rect is a list with the `dimensions` [left, bottom, width, height] of the new axes. We need to pass the values as a sequence of floats. All quantities are in fractions of figure width and height. The following code will create one axes the size of figure.
---
type: live-code
id: 5d696deb-39df-4fba-ac93-2dfe1263a9cd
code: |
  import matplotlib.pyplot as plt
  fig = plt.figure()
  ax = fig.add_axes([0,0,1,1])
  plt.show()
--- |
  This is how we create multiple axes objects of size (0.5, 0.5) at coordinates (0,0), (0,1), (1,0) and (1,1) respectively.
---
type: live-code
id: bb82999e-4b97-4362-9532-660758a40c6b
code: |
  import matplotlib.pyplot as plt
  fig = plt.figure()
  ax1 = fig.add_axes([0,0,0.5,0.5])
  ax2 = fig.add_axes([1,0,0.5,0.5])
  ax3 = fig.add_axes([0,1,0.5,0.5])
  ax4 = fig.add_axes([1,1,0.5,0.5])
  plt.show()
--- |
  The most prefered method to add axes is [add_subplot](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure.add_subplot) as matplotlib takes care of the exact positioning.

  The calling signature of  add_subplot is either a `3-digit integer` or three separate integers describing the position of the subplot. If the three integers are `nrows`, `ncols`, and `index` in order, the subplot will take the index position on a grid with nrows rows and ncols columns. Index starts at 1 in the upper left corner and increases to the right. `221` denotes first subplot of the total 4 subplots arranged in 2 rows and 2 columns. `111` represents the single subplot.
---
type: live-code
id: f4ed4742-8cb1-4762-bfed-f4c1014002e9
code: |
  import matplotlib.pyplot as plt
  fig = plt.figure()
  ax = fig.add_subplot(111)
  plt.show()
---
type: live-code
id: f07234b4-8987-4fb7-92f3-cc3768951389
code: |
  import matplotlib.pyplot as plt
  fig = plt.figure()
  ax1 = fig.add_subplot(221)
  ax2 = fig.add_subplot(222)
  ax3 = fig.add_subplot(223)
  ax4 = fig.add_subplot(224)
  plt.show()
--- |
  ### Adding Axes using state-based interface (pyplot)
  In [matplotlib.pyplot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.html#module-matplotlib.pyplot) various states are preserved across function calls, so that it keeps track of the current figure and plotting area, and the plotting functions are directed to the current axes.
  The first call to plt.plot will automatically create the necessary `figure` and `axes` to achieve the desired plot. Subsequent calls to plt.plot re-use the current axes and each add another line.

  A plot with single axes can be created using [matplotlib.pyplot.subplots](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplots.html) which creates a figure with 1 subplot by default(nrows=1, ncols=1).
---
type: live-code
id: d14876c9-91f5-4e2f-86d4-72546ebcc308
code: |
  import matplotlib.pyplot as plt
  fig, ax = plt.subplots()
  plt.show()
--- |
  A figure with more subplots can be created by specifying the number of `rows` and `columns` in the subplot grid. Here ax is a 2-D numpy array of shape (nrows, ncols) and we can plot data on a particular axes using ax[row inex, col index].
---
type: live-code
id: e7bd45cb-e346-4d54-a1d2-9ee9f3e46aa5
code: |
  import matplotlib.pyplot as plt
  fig, ax = plt.subplots(nrows=3, ncols=2)
  plt.show()
--- |
  Subplots can also be added to a current figure using  [matplotlib.pyplot.subplot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplot.html) which is a wrapper of [Figure.add_subplot](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure.add_subplot).
---
type: live-code
id: 6936cbb4-7f6d-49df-a5b6-5796018a0973
code: |
  import matplotlib.pyplot as plt
  ax1=plt.subplot(221)
  ax2=plt.subplot(222)
  plt.show()
---
