title: Scatter Plot
--- |
  [Scatter plot](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.scatter.html#matplotlib-pyplot-scatter) is used to visualize relationship between two or more variables. The correlation between variables can be positive, negative or zero(no correlation). The default marker style is is 'o'. Scatter plot can be used to represent data for a third or a forth variable using the size and color of markers.
---
type: live-code
id: 14cbc8a2-4915-4c3a-9f04-6e6baff1c634
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  iris = pd.read_csv('data/iris.csv')
  plt.scatter(iris['petal_length'],iris['petal_width'])
  plt.title('Scatter plot of petal length vs petal width in iris')
  plt.xlabel('petal length')
  plt.ylabel('petal width')
  plt.show()
--- |
  A third variable can be introduced in the form of a different color using the parameter c.
---
type: live-code
id: a5ab1cfd-e06f-42b0-865a-c5a5456c127e
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  iris = pd.read_csv('data/iris.csv')

  # Encode species
  species = iris['species'].map({'setosa':0, 'versicolor': 1, 'virginica': 2})

  plt.scatter(iris['petal_length'],iris['petal_width'], c = species, marker = '<')
  plt.title('Scatter plot of petal length vs petal width in iris')
  plt.xlabel('petal length')
  plt.ylabel('petal width')
  plt.show()
--- |
  A scatter plot with 4 variables can be created using color and size of the dots to represent the 3rd and the 4th variables.
---
type: live-code
id: b2cac5ee-c780-41dc-9653-b592b4723b0e
code: |
  import matplotlib.pyplot as plt
  import pandas as pd
  import numpy as np

  titanic = pd.read_csv('data/titanic.csv')

  fig, ax = plt.subplots(figsize = (12,8))

  # Remove outliers in fare
  titanic = titanic[np.abs(titanic['fare'] - titanic['fare'].mean()) <= (3 * titanic['fare'].std())]

  age = titanic['age']
  fare = titanic['fare']
  titanic_sex = titanic['sex'].map({'male' : 1, 'female' : 2})
  titanic_survived = titanic['survived']

  ax.scatter(age, fare, alpha = 0.2, c = titanic_survived, s =  titanic_sex * 300, cmap = 'coolwarm')
  ax.set_xlabel('Age')
  ax.set_ylabel('Fare')
  ax.set_title('Scatter plot of Age and Fare in titanic by sex and survival')
  plt.show()
---
