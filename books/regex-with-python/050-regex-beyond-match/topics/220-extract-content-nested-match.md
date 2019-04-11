title: Extract Nested Match
--- |

  Let's look at another problem of extracting content. This time, we are given a list of people's names (e.g. `Ram Kripal`, `John Smith`, `Lee Cheung` etc). We need to extract the first name and the last name.

  One approach is to define two regex: one for extracting first name and another for extracting last name.

  ```Python
  >>> import re
  >>>
  >>> first_name_match = re.search(r"^\w+", "Ram Kripal")
  >>> first_name_match.group()
  'Ram'
  >>> last_name_match = re.search(r"\w+$", "Ram Kripal")
  >>> last_name_match.group()
  'Kripal'
  ```

  This is not very efficient as we had to create two separate regex. Regex allows us to create multiple groups within a single regex. Then, we can extract content corresponding to each of those groups.

  ```Python
  >>> import re
  >>>
  >>> name_match = re.search(r"(\w+) (\w+)", "Ram Kripal")
  >>> name_match.group() # same as name_match.group(0)
  'Ram Kripal'
  >>> name_match.group(1)
  'Ram'
  >>> name_match.group(2)
  'Kripal'
  ```

  In this case, each pattern defined within `()` becomes yet another match group. The full match is always the group 0. After that, each `()` leads to the next group number. You can play with this code here:

---
type: live-code
id: 944552b5-f326-4b2e-820d-e08a71ffdf87
code: |
  import re

  name_match = re.search(r"(\w+) (\w+)", "Ram Kripal")
  print('Full Name', name_match.group())
  print('First Name', name_match.group(1))
  print('Last Name', name_match.group(2))

--- |

  We can modify this example to also handle middle name as well.

  ```Python
  >>> import re
  >>>
  >>> # first example of a person with middle name
  >>> name_match = re.search(r"(\w+) (\w*)\b\s?(\w+)", "Ram Prakash Kripal")
  >>> name_match.group(0)
  'Ram Prakash Kripal'
  >>> name_match.group(1)
  'Ram'
  >>> name_match.group(2)
  'Prakash'
  >>> name_match.group(3)
  'Kripal'
  >>>
  >>> # next example of a person without middle name. same regex.
  >>> name_match = re.search(r"(\w+) (\w*)\b\s?(\w+)", "Ram Kripal")
  >>> name_match.group(0)
  'Ram Kripal'
  >>> name_match.group(1)
  'Ram'
  >>> name_match.group(2)
  ''
  >>> name_match.group(3)
  'Kripal'
  ```

---
type: coding-question
id: 8a9f5ede-33d8-4d92-a0b1-94dc9c8170af
question: |
  Write a function `extract_site_name` that takes a string as input. If the string is a valid url (i.e. `http://www.<site>.com`), it returns the `<site>`. Otherwise, it returns `None`.

code: |
  # import goes here

  def extract_site_name(s):
      # codes goes here

tests: |
  assert extract_site_name('http://www.google.com') == 'google'
  assert extract_site_name('http://www.yahoo.com') == 'yahoo'
  assert extract_site_name('http://www.facebook.com') == 'facebook'
  assert extract_site_name('www.facebook.com') == None
  assert extract_site_name('facebook.com') == None

solution: |
  import re

  def extract_site_name(s):
      m = re.search(r"^http://www\.(\w+)\.com", s)
      if not m:
          return None

      return m.group(1)

---
type: coding-question
id: f2017509-009a-42a7-b33b-3c68b915d971
question: |
  Write a function `extract_host_site_name` that takes a string as input. If the string is a valid url (i.e. `http://<host>.<site>.com`), it returns a tuple of the form `(<host>,<site>)`. Otherwise, it returns `None`.

code: |
  # import goes here

  def extract_host_site_name(s):
      # codes goes here

tests: |
  assert extract_host_site_name('http://mail.google.com') == ('mail', 'google')
  assert extract_host_site_name('http://en.wikipedia.org') == ('en', 'wikipedia')
  assert extract_host_site_name('http://www.facebook.com') == ('www', 'facebook')
  assert extract_host_site_name('www.facebook.com') == None
  assert extract_host_site_name('facebook.com') == None

solution: |
  import re

  def extract_host_site_name(s):
      m = re.search(r"^http://(\w+)\.(\w+)\.com", s)
      if not m:
          return None

      return (m.group(1), m.group(2))

---
type: coding-question
id: f2017509-009a-42a7-b33b-3c68b915d971
question: |
  Suppose you have a list of items with their quantities as follows:

  ```
  spoons: 4
  bowls: 6
  cups: 8
  ```

  Your task is to write a function `extract_item_quantity` that takes a string as input. The string is of the format `<item>: <quantity>`. The function returns a tuple of the format `(<item>, <quantity>)` if it finds the input string in correct format. Otherwise, it returns `None`.

  Note: the `<quantity>` should be returned as integer.

code: |
  # import goes here

  def extract_item_quantity(s):
      # codes goes here

tests: |
  assert extract_item_quantity('spoons: 4') == ('spoons', 4)
  assert extract_item_quantity('bowls :6') == ('bowls', 6)
  assert extract_item_quantity('cups   :   8') == ('cups', 8)
  assert extract_item_quantity('pans: ') == None
  assert extract_item_quantity(': 4') == None
