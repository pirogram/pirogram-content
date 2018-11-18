title: Customizing Plots
--- |
  The matoplotlib plots can be customized to by changing the [Color](https://matplotlib.org/api/colors_api.html#module-matplotlib.colors), [Line-style](https://matplotlib.org/gallery/lines_bars_and_markers/line_styles_reference.html#line-style-reference), linewidth, [Markers](https://matplotlib.org/api/markers_api.html) and Markersize.
  ### Object-oriented interface
  Style parameter can be added to plot by specifying line `color` and `style` together. The following example shows a line plot with dotted-line style and black color(code: k).
---
type: live-code
id: 3d7d8a57-16d8-4de4-b922-0df45acf9d49
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  fig, ax = plt.subplots()
  ax.set_title('Plot with black dotted-line style')
  ax.plot(x, y, 'k--')
  plt.show()
--- |
  `Linewidth` can also be customized using the parameter by same name.
---
type: live-code
id: 1d5f3f21-53ae-467e-8026-f92d152c8820
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  fig, ax = plt.subplots()
  ax.plot(x, y, 'b--', linewidth = 3)
  ax.set_title('Plot with blue dotted-line style and linewidth 3')
  plt.show()
--- |
  [Markers](https://matplotlib.org/api/markers_api.html#module-matplotlib.markers) are individual points on the line. Marker with a specific style can be added using `marker` and the size of the marker is customized using `markersize`.
---
type: live-code
id: 5a9c8f29-d797-4484-a343-28dad68c1045
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  fig, ax = plt.subplots()
  ax.plot(x, y, 'r-.', linewidth = 2, marker = 'o', markersize=5)
  ax.set_title('Plot with red dash-dotted line and marker')
  plt.show()
--- |
  ### Using pyplot
---
type: live-code
id: 48b46cb4-96de-4f6c-835a-b27d3d542bf7
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  plt.plot(x, y, 'g--', linewidth=2, marker = '^',markersize=9)
  plt.title('Plot with green dotted line and triangle_up marker of size 9')
  plt.show()
--- |
  Markers can be placed on a subset of points based on index rather than on all the points using parameter `markevery`.
---
type: live-code
id: b60dec12-fe51-493c-b570-954bc981cef8
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)  
  markers_on = [51, 75, 95, 118]
  plt.plot(x, y, 'bD--', markevery=markers_on, linewidth = 1)

  plt.show()
