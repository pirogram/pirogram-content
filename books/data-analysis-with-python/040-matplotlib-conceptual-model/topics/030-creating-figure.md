title: Creating Figure
--- |
  ### Creating figure using `object-oriented interface`
  In the The first level of the object-oriented interface, pyplot is used only for a few functions such as figure creation. The user explicitly creates and keeps track of the figure and axes objects. Here is a way to create a `figure` object of class [matplotlib.figure.Figure](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib-figure-figure). `Please note that creating figure using plt.figure() does not automatically create an axes and hence all you can see is the figure object.`
---
type: live-code
id: dd6cfa26-2e2f-4191-971b-868c7e1af27d
code: |
  import matplotlib.pyplot as plt
  fig = plt.figure()
  print(type(fig))  
--- |
  The figure object can be customized by using various parameters in [figure.Figure](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html). Example: We can specify the size of the figure using the parameter `figsize`. It is the figure dimension (width, height) in inches. We can also change the `linewidth`.
---
type: live-code
id: a6ba17a2-4bda-4dda-818c-0723389195f4
code: |
  import matplotlib.pyplot as plt
  fig = plt.figure(figsize = (10,5), linewidth = 3)
--- |
  ### Creating figure using state-based interface (pyplot)
  In [matplotlib.pyplot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.html#module-matplotlib.pyplot) various states are preserved across function calls, so that it keeps track of the current figure and plotting area, and the plotting functions are directed to the current axes.
  As we mentioned in the introduction, Pyplot iterface is easier for simple plots. The first call to plt.plot will automatically create the necessary figure and axes to achieve the desired plot. Subsequent calls to plt.plot re-use the current axes and each add another line. `Since pyplot plot automatically adds axes at the time of figure creation, you can see the figure.` The plot is empty because we haven't specified any values at X and Y axis.
---
type: live-code
id: ad9fcbd2-b260-4bb4-a5d8-366a1d136c68
code: |
  import matplotlib.pyplot as plt
  plt.plot()
  plt.show()
---
