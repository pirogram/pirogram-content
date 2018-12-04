title: Matplotlib Conceptual model
---
  Matplotlib is a Python library for creating 2 dimensional plots. It provides a stateless `object-oriented interface` for plotting. It can be used in Python scripts, Python and IPython shells, Jupyter notebooks and web application servers.
  Object-oriented interface is the most powerful and preferred way of plotting as it provides complete control over the plot. The user generates and keeps track of the figure and axes objects. These axes objects are then used for most plotting actions. This proves especially useful while dealing with a figure containing multiple axes (multiple plots).

  Pyplot is a module in matplotlib which provides the `state-based interface` to the underlying object-oriented plotting library.
  In Pyplot various states are preserved across function calls, so that it keeps track of the current figure and plotting area, and the plotting functions are directed to the current axes. The plotting framework provided by pyplot is more convenient. It provides command style functions for making changes to the figure.

  To summarize, Pyplot is very effective for simple plotting whereas the object oriented interface is the way to go when the user requires more control over the plot.

  Was the explanation confusing enough? The following topics are aimed at removing the confusion piece by piece :)
