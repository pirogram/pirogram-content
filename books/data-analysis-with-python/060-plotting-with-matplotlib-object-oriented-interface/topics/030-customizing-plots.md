title: Customizing Plots
--- |
  ### Figure size
  The default figure size is 6.4 X 4.8 inches. Figure size can be changed by passing a tuple of integers to the optional parameter `figsize` in [pyplot.subplots](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.subplots.html#matplotlib.pyplot.subplots).

  ### Color, style and markers
  Matplotlib supports various optional formatting parameters  like `color`, `marker` and `linestyle`.

  The following `color` abbreviations are supported:
  * 'b'	blue
  * 'g'	green
  * 'r'	red
  * 'c'	cyan
  * 'm'	magenta
  * 'y'	yellow
  * 'k'	black
  * 'w'	white   

  Besides the abbreviations, Matplotlib recognizes the formats like full name (eg: 'black') or hex strings ('#0F0F0F'). You can find the supported formats and full range of colors at [matplotlib.colors](https://matplotlib.org/api/colors_api.html#module-matplotlib.colors).

  `Marker` is another optional formatting parameter with the default being None. You can take a look at all possible [matplotlib.markers] (https://matplotlib.org/api/markers_api.html#module-matplotlib.markers).

  `Linestyle` is the third optional formatting parameter with the default being solid line ('-'). Here is the [linestyle reference](https://matplotlib.org/gallery/lines_bars_and_markers/line_styles_reference.html#line-style-reference).

  ### Linewidth
  Another line property that we can control is linewidth. The default line width is 1.5 points.

  ### Gridlines
  Gridlines helps with readability of the data points and we can configure gridlines using [Axes.grid](https://matplotlib.org/api/_as_gen/matplotlib.axes.Axes.grid.html#matplotlib.axes.Axes.grid). Either set any of the kwargs (`color`, `linestyle`, `linewidth`) or set parameter `b` to True to show the gridlines. We can also choose the `axis` on which we want to apply the gridlines with default being `both`.

  Here is a figure of size (9,5) and plot with linewidth set to 3.
---
type: live-code
id: 1d5f3f21-53ae-467e-8026-f92d152c8820
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 11)
  y = x ** 2
  fig, ax = plt.subplots(figsize = (9,5))
  ax.plot(x, y , linewidth = 3)
  plt.show()
--- |
  Let us change the `color` and `linestyle` of the above plot using the parameters we discussed.
---
type: live-code
id: 3d7d8a57-16d8-4de4-b922-0df45acf9d49
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 11)
  y = x ** 2
  fig, ax = plt.subplots()
  ax.plot(x, y, color = 'k', linestyle = '--')
  plt.show()
--- |
  [Markers](https://matplotlib.org/api/markers_api.html#module-matplotlib.markers) are individual points on the line. Marker with a specific style can be added using `marker` and the size of the marker is customized using `markersize`.
---
type: live-code
id: 5a9c8f29-d797-4484-a343-28dad68c1045
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 11)
  y = x ** 2
  fig, ax = plt.subplots()
  ax.plot(x, y, color = 'r', linestyle = '-.', linewidth = 2, marker = 'o', markersize=5)
  plt.show()
--- |
  Finally, the style parameters `color`, `marker` and `linestyle` can be combined in a `shortcut string notation` as shown in the example here. We will also add `figsize`, `markersize` and `linewidth` to the style parameters and add gridlines.
---
type: live-code
id: 6fb3cae8-2594-4e46-946c-8341d48270ee
code: |
  import matplotlib.pyplot as plt
  import numpy as np

  x = np.arange(-10, 11)
  y = x ** 2
  fig, ax = plt.subplots(figsize = (8,4))
  ax.plot(x, y, 'ro-.', linewidth = 2, markersize=5)
  ax.grid(color = 'k')
  plt.show()
---
