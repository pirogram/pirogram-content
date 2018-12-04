title: Understanding Matplotlib object hierarchy
--- |
  Matplotlib plot is created using a hierarchy of python objects. Lets look at the hierarchy to understand the terms like figure, axes that we used in the introduction. Here is a diagram of matplotlib hierarchy with every component.

  ![Matplotlib Anatomy](assets/img/matplotlib_anatomy.png)

  ### Figure
  The outermost object is the figure which is an instance of [figure.Figure](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html). It is the top level container for all the plot elements. The Figure is the final image that may contain 1 or more `Axes` and it keeps track of all the `Axes`. `Figure is only a container and you can not plot data on figure.`

  ### Axes
  Axes is the instance of [matplotlib.axes.Axes](https://matplotlib.org/api/axes_api.html#matplotlib.axes.Axes). `Axes is the area on which data are plotted.` The Axes contains most of the figure elements: Axis, Tick, Line2D, Text, Polygon and sets the coordinate system. A given figure can contain many Axes, but a given Axes object can only be in one Figure.

  ### Axis
  Axis is the instance of [matplotlib.axis.Axis](https://matplotlib.org/api/axis_api.html#axis-objects). Axis instances handle the drawing of the tick lines, the grid lines, the tick labels and the axis label. The location of the ticks is determined by a Locator object and the tick label strings are formatted by a Formatter. The combination of the correct Locator and Formatter gives very fine control over the tick locations and labels.

  ### Artist
  Everything on the figure, including Figure, Axes, and Axis objects, is an artist. This includes Text objects, Line2D objects, collection objects, Patch objects. When the figure is rendered, all of the artists are drawn to the canvas. A given artist can only be in one Axes.

---
