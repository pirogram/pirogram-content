title: Loading data from file formats
--- |
  Data from file formats like csv, txt, tables, json can be easily read into a pandas DataFrame. Here are some of the formats that can be converted to a DataFrame using Pandas.

  ### Comma separated files (csv)
  [pandas.read_csv](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.read_csv.html) method is used to load the data in csv format into a DataFrame. It includes various optional parameters, we will look at some of them.
---
type: live-code
id: ba68d905-45b1-4e85-b3a9-35d48c6baa5d
code: |
  import pandas as pd
  iris = pd.read_csv('data/pandas/iris.csv')
  iris.head()
--- |
  #### Working with different separators
  If the csv you are trying to read is not comma separated, use the parameter sep. Lets read a semi-colon separated file.
---
type: live-code
id: 56ca0710-6487-486e-8423-a822847440b8
code: |
  import pandas as pd
  df = pd.read_csv('data/pandas/semicolon_sep.csv')
  df
--- |
  The resulting DataFrame contains all the entries in same column as the default separator comma was not present. Now lets try again by passing semi-colon as separator. Similarly, tables can be read using read_csv by specifying '\t' as separator.
---
type: live-code
id: b0782fa1-a818-49fe-9eb6-6a915fedc9cd
code: |
  import pandas as pd
  df = pd.read_csv('data/pandas/semicolon_sep.csv', sep = ';')
  df
--- |
  #### Handling Encoding

  Reading encoded csv file will throw UnicodeDecodeError. You can pass the appropriate encoding to read the file. Here is a list of standard encodings (https://docs.python.org/3/library/codecs.html#standard-encodings)
---
type: live-code
id: 78ee9986-f47e-46f8-867c-42e057c41cb1
code: |
  import pandas as pd
  df = pd.read_csv('encoded.csv', encoding = 'utf-8')
  df
--- |
  ### Reading data from table
  Pandas method read_table was available to read data from table. The method is Deprecated since version 0.24.0. You can read data from table using read_csv by passing `\t` as separator.
--- |
  ### Reading data from json
  [pandas.read_json](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_json.html) is used to Convert a VALID JSON string or file handle / StringIO to pandas object. The string could be a URL. The parameter `orient` is used to align index and columns. For Series, the default orientation is `index` whereas other allowed values are `split` & `records`. For DataFrame, the default is columns whereas other allowed values are `split`, `record`, `index`, `values` & `table`.
---
type: live-code
id: 37a972a0-dd6f-4644-8c43-9df7ac93bb05
code: |
  import pandas as pd
  data = '{"row 1":{"col 1":"a","col 2":"b"},"row 2":{"col 1":"c","col 2":"d"}}'
  df = pd.read_json(data, orient='index')
  df
---
type: live-code
id: e058c2e6-8479-42cd-8ffa-0b561d4e1b5d
code: |
  import pandas as pd
  d = '{"columns":["col 1","col 2"],"index":["row 1","row 2"],"data":[["a","b"],["c","d"]]}'
  df = pd.read_json(d, orient='split')
  df
---
type: live-code
id: 1a461929-68bc-4b18-a03b-4dab2c613cc1
code: |
  import pandas as pd
  data = '[{"col 1":"a","col 2":"b"},{"col 1":"c","col 2":"d"}]'
  df = pd.read_json(data, orient='records')
  df
---
type: live-code
id: 7ef8be65-fad1-4512-97b0-38d02f801b64
code: |
  import pandas as pd
  df = pd.read_json('https://api.github.com/repos/pydata/pandas/issues?per_page=5')
  df
