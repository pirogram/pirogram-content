title: Customizing plots
--- |

  ### Figure size
  The default figure size is 6.4 X 4.8 inches. We change the figure size by passing a tuple of integers to the optional parameter figsize in [matplotlib.pyplot.figure](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.figure.html#matplotlib-pyplot-figure).

  ### Format Color, style and markers
  The pyplot plot command incorporates various optional parameters to conveniently define basic formatting like `color`, `marker` and `linestyle`.
  The following color abbreviations are supported:
  * 'b'	blue
  * 'g'	green
  * 'r'	red
  * 'c'	cyan
  * 'm'	magenta
  * 'y'	yellow
  * 'k'	black
  * 'w'	white   
  Besides the abbreviations, Matplotlib recognizes the formats like full name (eg: 'black') or hex strings ('#0F0F0F'). You can find the supported formats and full range of colors at [matplotlib.colors](https://matplotlib.org/api/colors_api.html#module-matplotlib.colors).

  Marker is another optional formatting parameter with the default being None. You can take a look at all possible [matplotlib.markers] (https://matplotlib.org/api/markers_api.html#module-matplotlib.markers).

  Linestyle is the third optional formatting parameter with the default being solid line ('-'). Here is the [linestyle reference](https://matplotlib.org/gallery/lines_bars_and_markers/line_styles_reference.html#line-style-reference).

  ### Linewidth
  Another line property that we can control is linewidth. The default line width is 1.5 points.

  Lets start by creating a figure of size (8,4) and plot with linewidth set to 5.
---
type: live-code
id: b0a079fa-5f36-4d42-bac3-9d4d9cd8f3bc
code: |
  import numpy as np
  import matplotlib.pyplot as plt

  x = np.arange(5)
  y = x ** 2
  plt.figure(figsize = (8, 4))
  plt.plot(x, y, linewidth = 5)
  plt.show()
--- |
  Let us change the color and style of the above plot using the parameters we discussed.
---
type: live-code
id: dda11748-b87a-4e42-8813-8da2050c87ad
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(5)
  y = x ** 2
  plt.plot(x, y, color='red', marker='o', linestyle='dashed')
  plt.show()
--- |
  Matplotlib allows us to combine the line properties and format in one string. The following shortcut notation in plot command will generate a plot with same color('r'), marker('o') and linestyle('--')
---
type: live-code
id: f78676fa-16cd-4409-9bd2-1f031da67c72
code: |
  import numpy as np
  import matplotlib.pyplot as plt
  x = np.arange(5)
  y = x ** 2
  plt.figure(1)
  plt.plot(x, y, 'ro--')
  plt.show()
---
