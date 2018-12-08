title: Matplotlib Conceptual model
--- |
  Matplotlib is the most extensively written and commonly used  Python library for visualizing data. It provides a stateless `object-oriented interface` for plotting. It can be used in Python scripts, Python and IPython shells, Jupyter notebooks and web application servers.

  Plotting requires action on a range of levels, ranging from the size of the figure to the text object in the plot. Matplotlib provides object oriented interface in the hierarchical fashion to provide complete control over the plot. The user generates and keeps track of the figure and axes objects. These axes objects are then used for most plotting actions. This proves especially useful while dealing with a figure containing multiple axes (multiple plots).

  [Matplotlib.pyplot](https://matplotlib.org/tutorials/introductory/pyplot.html#pyplot-tutorial) is a module in the matplotlib package. Pyplot provides the state-machine interface to the underlying object-oriented plotting library. The state-machine implicitly and automatically creates figures and axes to achieve the desired plot.

  To understand these terms better, tets start by understanding the hierarchy of matplotlib objects.
