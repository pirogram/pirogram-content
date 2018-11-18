title: Customizing plots
--- |
  The `Axes` object consists of a pair of `axis` that contain a single plot (x-axis and y-axis). The Axes object has various methods to customize properties like plot frame (set_frame_on() or set_frame_off()), X and Y-axis limits (set_xlim() and set_ylim()), X and Y-axis Labels (set_xlabel() and set_ylabel()), plot title (set_title()) etc.

  ### Customize plot using object-oriented interface
  Define a figure with axes and call methods of ax directly to add `title` and set x and y-axis `labels`. Under the object-oriented approach, the [matplotlib.axis.Tick](https://matplotlib.org/api/axis_api.html#matplotlib.axis.Tick) is the final container object in the plot hierarchy. The ticks, labels, grid line instances are accessible directly as an attribute of the Tick.
---
type: live-code
id: 5d07812d-df1c-4cb6-95ea-7fe31f9f333e
code: |
  import matplotlib.pyplot as plt

  # Create figure and a single AxesSubplot object
  fig, ax = plt.subplots(figsize=(5, 3))

  # Set the title of the plot
  ax.set_title('My Plot title')

  # Set X label
  ax.set_xlabel('My X label')
  # Set Y label
  ax.set_ylabel('My Y label')

  # Set data limits for X axis
  ax.set_xlim(xmin=0, xmax=100)

  # Set y-tick labels with list of strings labels.
  ax.set_yticklabels(['20','40','custom tick','80','100'])

  plt.show()
--- |
  The same can also be achieved using [matplotlib.axes.Axes.set](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.set.html#matplotlib-axes-axes-set), a property `batch setter`.
---
type: live-code
id: 116bb1f9-e174-4adf-9397-e046e319bf72
code: |
  import matplotlib.pyplot as plt
  fig, ax = plt.subplots()
  ax.set(xlim=[0, 100], ylim = [0, 10],xlabel='My X label', ylabel='My Y label',title='My Plot title')
  plt.show()
--- |
  ### Customize plot using state-based interface (Pyplot)
  Pyplot offers convenient methods to set the axis parameters which access the corresponding setters in matplotlib for the `current axes`.
---
type: live-code
id: c413adb5-e87d-4dd0-94d1-1a55accb63d7
code: |
  import matplotlib.pyplot as plt
  plt.plot()

  # set the axis limits (xmin, xmax, ymin, ymax)
  plt.axis([0,20, 0, 50])

  # Set X-axis labels
  plt.xlabel('My X Label')
  # Set Y-axis labels
  plt.ylabel('My Y Label')

  # Set the plot title
  plt.title('My Plot title')

  plt.show()
---
