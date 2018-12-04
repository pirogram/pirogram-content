title: Adding Axes
--- |
  ### Adding Axes using object-oriented interface
  Axes is the part of the figure with individual plots or graphs. One or more `axes` objects are added to `figure` to enable plotting. Pyplot automatically adds axes while creating figure as we saw in the earlier section.

  There are two ways of adding axes using stateless (object-oriented interface), [add_axes](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure.add_axes) or [add_subplot](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure.add_subplot). They both return a matplotlib.axes.Axes object.

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
--- |
  ### Adding Axes using state-based interface (pyplot)
  In [matplotlib.pyplot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.html#module-matplotlib.pyplot) various states are preserved across function calls, so that it keeps track of the current figure and plotting area, and the plotting functions are directed to the current axes.
  The first call to plt.plot will automatically create the necessary `figure` and `axes` to achieve the desired plot. Subsequent calls to plt.plot re-use the current axes and each add another line.

  A plot with single axes can be created using [matplotlib.pyplot.subplots](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplots.html) which creates a figure with 1 subplot by default(nrows=1, ncols=1). At the default setting, it gives similar output as plt.plot().
---
type: live-code
id: d14876c9-91f5-4e2f-86d4-72546ebcc308
code: |
  import matplotlib.pyplot as plt
  fig, ax = plt.subplots()
  plt.show()
---
type: testless-coding-question
id: 1f8bf560-8571-4cea-afaf-2f43c976000d
question: |
  Create a matplotlib figure of size (10,4) and add a single axes. Display the figure and axes.
code: |
  # Your code goes here
---
type: testless-coding-question
id: 84adeba6-f2a0-48f4-8b90-b130b68e00e5
question: |
  Create a matplotlib figure and single subplot using `pyplot` interface
code: |
    # Your code goes here
---
