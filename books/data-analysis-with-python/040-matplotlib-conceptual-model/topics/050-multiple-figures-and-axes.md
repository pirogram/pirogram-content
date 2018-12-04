title: Multiple figure and axes
--- |
  [matplotlib.axes.Axes](https://matplotlib.org/api/axes_api.html#matplotlib.axes.Axes) contains most of the figure elements like Axis, Tick, Line2D, Text, Polygon, etc., and sets the coordinate system. Axes allow placement of plots at any location in the figure, eg: a smaller plot overlaid on a bigger one.

  There are various ways of creating a matplotlib figure with multiple axes.
  * add_axes(rect): rect is a list with the `dimensions` [left, bottom, width, height] of the new axes. All quantities are in fractions of figure width and height. This allows greater control over the figure with precisely placed axes including overlapping axes.
  * add_subplot(nrows, ncols, index): `3-digit integer` or three separate integers describing the position of the subplot. `111` represents the single subplot. Matplotlib takes care of the exact positioning of the subplots making it convenient but with less control compared to add_axis.
  * pyplot.subplots(nrows, ncols): `Create a figure and a set of subplots` in a single call. It returns a figure and an axes. The axes would be a single Axes object in case of default setting (nrows = 1, ncols = 1) or an array of Axes objects if more than one subplot was created. Incase of multiple axes, we plot data on a particular axes using ax[row index, col index].
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
  The flexibility add_axis offers in terms of being able to control the exact location and size of axes comes with a cost. It is a lot more complicated to create a figure with more than two axes in one row. Here is an example that creates a figure with three axes located side by side. Notice how we set the width and height of each axes at (0.3, 0.3) and positioned the first axes at 0, second at 0.4 to avoid overlapping the first axes of size 0.3 and the third at 0.9.
---
type: live-code
id: 02487e99-6dca-4af2-b682-5156a862721d
code: |
  import matplotlib.pyplot as plt
  fig = plt.figure()
  ax1 = fig.add_axes([0.1, 0.2, 0.3, 0.3])
  ax2 = fig.add_axes([0.5, 0.2, 0.3, 0.3])
  ax3 = fig.add_axes([0.9, 0.2, 0.3, 0.3])
  plt.show()
--- |
  The most prefered method to add axes is [add_subplot](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure.add_subplot) as matplotlib takes care of the exact positioning.

  The calling signature of  add_subplot is either a `3-digit integer` or three separate integers describing the position of the subplot. If the three integers are `nrows`, `ncols`, and `index` in order, the subplot will take the index position on a grid with nrows rows and ncols columns. Index starts at 1 in the upper left corner and increases to the right. `221` denotes first subplot of the total 4 subplots arranged in 2 rows and 2 columns. `111` represents the single subplot.
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
  A plot with single axes can be created using [matplotlib.pyplot.subplots](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplots.html) which creates a figure with 1 subplot by default(nrows=1, ncols=1). At the default setting, it gives similar output as plt.plot(). The main reason for using pyplot subplots() would be to `create a figure and a set of subplots`. A figure with more subplots can be created by specifying the number of `rows` and `columns` in the subplot grid. Here ax is a 2-D numpy array of shape (nrows, ncols) and we can plot data on a particular axes using ax[row inex, col index].
---
type: live-code
id: e7bd45cb-e346-4d54-a1d2-9ee9f3e46aa5
code: |
  import matplotlib.pyplot as plt
  fig, ax = plt.subplots(nrows=3, ncols=2)
  plt.show()
---
type: testless-coding-question
id: 811199e0-7438-41a0-bdf3-2b2fffaa330e
question: |
  Create a matplotlib figure and add an inset axes at the top-right corner of another axes. Hint: The main axes will cover the entire figure whereas the inset axes should be created using add_axes(rect). The resulting figure with axes should look like this:
  ![Matplotlib Figure with inset axes](assets/img/axes_inset.png)
code: |
  # Your code goes here. 

---
type: testless-coding-question
id: 83d3b137-e60c-4be6-a6dd-8f36e015fcd7
question: |
  Create a matplotlib figure of size (10,5) and use `object oriented` interfact to add subplots such that the resulting figure has total 6 subplots arranged in 3 rows and 2 columns.
code: |
  # Your code goes here
---
