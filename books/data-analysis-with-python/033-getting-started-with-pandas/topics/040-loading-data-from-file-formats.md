title: Loading data from file formats
--- |
  Data from various file formats can be loaded into a pandas DataFrame. Here are some of the formats that can be converted to a DataFrame using Pandas.

  ### Comma separated files (csv)
  [pandas.read_csv](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.read_csv.html) method is used to load the data in csv format into a DataFrame.
---
type: live-code
id: ba68d905-45b1-4e85-b3a9-35d48c6baa5d
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  iris.head()
--- |
  ### Tables
  [pandas.read_table](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.read_table.html) is used to read general delimited file into DataFrame.
  
