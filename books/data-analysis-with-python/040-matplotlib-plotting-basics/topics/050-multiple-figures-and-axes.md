title: Multiple figures and Axes
--- |
  ### Using object-oriented interface to work with multiple figures and Axes
---
type: live-code
id: 5d1c85c7-a232-480c-8599-f64eaba7f862
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  z = np.cos(x)

  fig = plt.figure()
  ax1 = fig.add_subplot(211)
  ax2 = fig.add_subplot(212)

  ax1.plot(x, y)
  ax1.set_title('Sine wave')

  # Remove xticks to avoid overlapping ticks on ax2 title.
  ax1.set_xticks([])

  ax2.plot(x, z)
  ax2.set_title('Cos wave')

  plt.show()  
--- |
  ### Using Pyplot to work with multiple figures and Axes
---
type: live-code
id: 41ec4f69-4a94-4170-a1db-9a6c1d78200a
code: |
  import matplotlib.pyplot as plt
  import numpy as np
  
  x = np.arange(-10, 10, 0.1)
  y = np.sin(x)
  z = np.cos(x)

  plt.subplot(211)
  plt.plot(x, y)
  plt.title('Sine wave')
  plt.xticks([])

  plt.subplot(212)
  plt.plot(x, z)
  plt.title('Cos wave')

  plt.show()
---
