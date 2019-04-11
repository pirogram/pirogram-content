title: split() / findall()
--- |

  We'll run through a few more methods in the `re` module.

  ## re.split()

  The `re.split()` method splits a strings based on a regex. Example:

  ```Python
  >>> import re
  >>>
  >>> re.split(r"\W+", "apple banana mango pickle")
  ['apple', 'banana', 'mango', 'pickle']
  >>>
  >>> re.split(r"\W+", "apple, banana, mango, pickle")
  ['apple', 'banana', 'mango', 'pickle']
  >>>
  >>> re.split(r"\W+", "apple, banana , mango   , pickle")
  ['apple', 'banana', 'mango', 'pickle']
  ```

  While you can use the string's `split()` method, the regex one just becomes more powerful since it can handle so many variations of the separator.

  You can play with the code here:

---
type: live-code
id: 4372b810-83bc-44fd-8b7f-722862cb6f9e
code: |
  import re

  arr = re.split(r"\W+", "apple, banana , mango   , pickle")
  print(arr)

---
type: coding-question
id: f9965145-d7b0-46a5-a506-47afb703ffb0
question: |
  Let's say we are dealing with the following kind of data:

  ```
  spoons : 4
  bowls:2
  ```

  Write `REGEX_PATTERN` such that we can split the aforementioned kind of data in `item` and `quantity`.

code: |
  REGEX_PATTERN = r'...'

tests: |
  assert re.split(REGEX_PATTERN, 'Onion  :    2') == ['Onion', '2']
  assert re.split(REGEX_PATTERN, 'Onion:2') == ['Onion', '2']

solution: |
  REGEX_PATTERN = r'\s*:\s*'

--- |

  ## re.findall()

  The method `re.findall()` is useful when you are trying to find multiple occurrences of a pattern within text. For example, if we want to find all years mentioned in a given text, `findall()` would be pretty helpful. Example:

  ```Python
  >>> text = "The growth was more in 2001 compred to 2002."
  >>> re.findall(r"\d+", text)
  ['2001', '2002']
  ```

  You can play with the code here:

---
type: live-code
id: 25891334-dc44-4fed-b107-bd023d2a4bde
code: |
  import re

  text = "The growth was more in 2001 compred to 2002."
  years = re.findall(r"\d+", text)
  print(years)
