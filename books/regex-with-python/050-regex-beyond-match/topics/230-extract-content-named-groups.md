title: Extract Named Groups
--- |

  While it's possible (and easy) to use numbered groups to extract content, it can get unwiedly in complex regex when there are too many nested groups. It's much cleaner to be able to name the groups for which we want to extract the content.

  Let's rework the problem of extracting first name and last name from a name. This is what we did earlier:

  ```Python
  >>> name_match = re.search(r"(\w+) (\w+)", "Ram Kripal")
  >>> name_match.group(1)
  'Ram'
  >>> name_match.group(2)
  'Kripal'
  ```

  We can instead use the `(?P<group_name>...)` syntax:

  ```Python
  >>> name_match = re.search(r"(?P<first_name>\w+) (?P<last_name>\w+)", "Ram Kripal")
  >>> name_match.group('first_name')
  'Ram'
  >>> name_match.group('last_name')
  'Kripal'
  ```

  If you notice, we rewrote `(\w+)` as `(?P<first_name>\w+)` which can be broken down as:

  * `(` - start of the group.
  * `?P` - declaration that we'll give a name to the group.
  * `<first_name>` - name of the group.
  * `\w+` - pattern.
  * `)` - end of the group

  You can play with the code here:

---
type: live-code
id: 6f235096-0f72-48f6-8f5e-b30ae6eaf294
code: |
  import re

  name_match = re.search(r"(?P<first_name>\w+) (?P<last_name>\w+)", "Ram Kripal")

  print('Full Name', name_match.group())
  print('First Name', name_match.group('first_name'))
  print('Last Name', name_match.group('last_name'))

---
type: coding-question
id: 21c05233-af76-41ea-8f32-0994dc758022
question: |
  Let's write a function `extract_middle_name` that takes a name as input. It returns the middle name of the person by using named groups in regex.

code: |
  import re

  # Define the REGEX_PATTERN. You should not have a need to modify anything
  # else in this code.
  REGEX_PATTERN = r"..."

  def extract_middle_name(name):
      match = re.search(REGEX_PATTERN, name)
      if not match:
          return None
      else:
          return match.group('middle_name')

tests: |
  assert extract_middle_name('George Bernard Shaw') == 'Bernard'
  assert extract_middle_name('Ram Prakash Kripal') == 'Prakash'

solution: |
  import re

  REGEX_PATTERN = r"\w+ (?P<middle_name>\w+) \w+"

  def extract_middle_name(name):
      match = re.search(REGEX_PATTERN, name)
      if not match:
          return None
      else:
          return match.group('middle_name')

---
type: coding-question
id: ea476223-38e5-49fd-b70a-79d62746bc9a
question: |
  Given a url of the form `http://www.<site>.com`, we want to extract the `<site>`. Define the variable `REGEX_PATTERN` using named groups such that:
  * if the url is not in the given format, the regex will not match.
  * if the url is in the given format, the named group `site` will have the site name.

code: |
  REGEX_PATTERN = r'...'

tests: |
  import re
  match = re.search(REGEX_PATTERN, 'http://www.google.com')
  assert match != None
  assert match.group('site') == 'google'

  match = re.search(REGEX_PATTERN, 'blah blah blah')
  assert match == None

solution: |
  REGEX_PATTERN = r'http://www\.(?P<site>\w+)\.com'

---
type: coding-question
id: dca25a5b-8579-4aad-ba20-1b7fc072c5f2
question: |
  Given a url of the form `http://<host>.wikipedia.org`, we want to extract the `<host>`. Define the variable `REGEX_PATTERN` using named groups such that:
  * if the url is not in the given format, the regex will not match.
  * if the url is in the given format, the named group `host` will have the host name.

code: |
  REGEX_PATTERN = r'...'

tests: |
  import re
  match = re.search(REGEX_PATTERN, 'http://en.wikipedia.org')
  assert match != None
  assert match.group('host') == 'en'

  match = re.search(REGEX_PATTERN, 'blah blah blah')
  assert match == None

solution: |
  REGEX_PATTERN = r'http://(?P<host>\w+)\.wikipedia\.org'
