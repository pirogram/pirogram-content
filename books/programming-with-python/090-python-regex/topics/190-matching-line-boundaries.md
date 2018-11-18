title: Matching Line Boundaries
--- |

  Just like words have boundaris that we can match with `\b`, lines also have boundaries that we can match with `^` (start of line) and `$` (end of line).

  Let's say we want to match movie names that start with a year. So, we should match `2001: A Space Odyssey` but not `Dracula A.D. 1972`. We could use the pattern `^\d{4}\b` to do just that.

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"^\d{4}\b"
  >>>
  >>> re.search(REGEX_PATTERN, "2009: Lost Memories")
  <_sre.SRE_Match object; span=(0, 4), match='2009'>
  >>>
  >>> re.search(REGEX_PATTERN, "Broadway Melody of 1940")
  >>> # Not a match
  >>>
  >>> re.search(REGEX_PATTERN, "44500 Max")
  >>> # Not a match
  >>>
  ```

  Similarly, we can use the pattern `\b\d{4}$` to match movie names that end with a year.

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"\b\d{4}$"
  >>>
  >>> re.search(REGEX_PATTERN, "Broadway Melody of 1940")
  <_sre.SRE_Match object; span=(19, 23), match='1940'>
  >>>
  >>> re.search(REGEX_PATTERN, "2009: Lost Memories")
  >>> # Not a match
  >>>
  >>> re.search(REGEX_PATTERN, "Amityville 1992: It's About Time")
  >>> # Not a match
  >>>
  >>> re.search(REGEX_PATTERN, "Super 23123")
  >>> # Not a match
  >>>
  ```
---
type: multiple-choice-question
id: 72adb2e8-b01c-4f29-8109-7d380d120d8c
question: |
  Which of the following would match the regex `^\d{4}$`:
options:
  - text: "1984"
    correct: true
  - text: "1971"
    correct: true
  - text: "2081"
    correct: true
  - text: AM1200
  - text: Class of 1999
  - text: "2001: A Space Odyssey"
  - text: "Daleks' Invasion Earth: 2150 A.D."

---
type: coding-question
id: 169bd30c-ca2c-468b-9319-5caf27f1efa7
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie name has only one word. Otherwise, it returns `False`.

code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Superman') == True
  assert match_movie_name('1984') == True
  assert match_movie_name('Spiderman Returns') == False
  assert match_movie_name('2001: A Space Odyssey') == False
  assert match_movie_name('AM1200') == True
  assert match_movie_name('I.Q.') == False

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r"^\w+$", movie_name):
          return True
      else:
          return False

---
type: coding-question
id: 5424bec4-03d0-4ab5-a8e4-3db4fda08841
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie name does not have any whitespace character (hint: `\S`). Otherwise, it returns `False`.

code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Superman') == True
  assert match_movie_name('1984') == True
  assert match_movie_name('Spiderman Returns') == False
  assert match_movie_name('2001: A Space Odyssey') == False
  assert match_movie_name('AM1200') == True
  assert match_movie_name('I.Q.') == True

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r"^\S+$", movie_name):
          return True
      else:
          return False

---
type: coding-question
id: 6c7ed823-0cc1-40de-a671-e988e9d44597
question: |
  Write a function `valid_url` that takes a string as input. It returns `True` if the string is a valid url. Otherwise, it returns `False`.

code: |
  # import goes here

  def valid_url(s):
      # code goes here

tests: |
  assert valid_url('http://www.google.com') == True
  assert valid_url('http://www.yahoo.com') == True
  assert valid_url('http://www.wattpad.com') == True
  assert valid_url('http:// google.com') == False
  assert valid_url('A url looks like http://www.google.com') == False

solution: |
  import re

  def valid_url(s):
      if re.search(r"^http://www\.\w+\.com$", s):
          return True
      else:
          return False

---
type: coding-question
id: 90bcd660-49e7-42fa-9f4a-64bb28720165
question: |
  Write a function `valid_url` that takes a string as input. It returns `True` if the string is a valid url. Otherwise, it returns `False`.

code: |
  # import goes here

  def valid_url(s):
      # code goes here

tests: |
  assert valid_url('http://www.google.com') == True
  assert valid_url('https://www.yahoo.com') == True
  assert valid_url('https://www.wattpad.com') == True
  assert valid_url('http:// google.com') == False
  assert valid_url('A url looks like http://www.google.com') == False

solution: |
  import re

  def valid_url(s):
      if re.search(r"^https?://www\.\w+\.com$", s):
          return True
      else:
          return False

---
type: coding-question
id: 695ab476-a23b-4cf2-a876-71c2a16bbeff
question: |
  Write a function `valid_url` that takes a string as input. It returns `True` if the string is a valid url. Otherwise, it returns `False`.

code: |
  # import goes here

  def valid_url(s):
      # code goes here

tests: |
  assert valid_url('http://www.google.com') == True
  assert valid_url('https://www.yahoo.com') == True
  assert valid_url('https://www.wattpad.com') == True
  assert valid_url('https://en.wikipedia.org/') == True
  assert valid_url('http:// google.com') == False
  assert valid_url('A url looks like http://www.google.com') == False

solution: |
  import re

  def valid_url(s):
      if re.search(r"^https?://www\.\w+\.(com|org)$", s):
          return True
      else:
          return False

---
type: coding-question
id: f2a8586f-01bb-4a33-93d4-45070c51530a
question: |
  Write a function `valid_url` that takes a string as input. It returns `True` if the string is a valid url. Otherwise, it returns `False`.

code: |
  # import goes here

  def valid_url(s):
      # code goes here

tests: |
  assert valid_url('http://www.google.com') == True
  assert valid_url('https://www.yahoo.com') == True
  assert valid_url('https://www.wattpad.com/tags/children') == True
  assert valid_url('https://en.wikipedia.org/') == True
  assert valid_url('http:// google.com') == False
  assert valid_url('A url looks like http://www.google.com') == False

solution: |
  import re

  def valid_url(s):
      if re.search(r"^https?://www\.\w+\.(com|org)[/\w]+$", s):
          return True
      else:
          return False

---
type: coding-question
id: e0d044cd-2577-431d-96da-ab139d9798f1
question: |
  Write a function `valid_url` that takes a string as input. It returns `True` if the string is a valid url. Otherwise, it returns `False`.

code: |
  # import goes here

  def valid_url(s):
      # code goes here

tests: |
  assert valid_url('http://www.google.com') == True
  assert valid_url('https://www.yahoo.com') == True
  assert valid_url('https://www.wattpad.com/tags/children') == True
  assert valid_url('https://en.wikipedia.org/') == True
  assert valid_url('http://localhost:8000/test-page.html') == True
  assert valid_url('http:// google.com') == False
  assert valid_url('A url looks like http://www.google.com') == False

solution: |
  import re

  def valid_url(s):
      if re.search(r"^https?:[\d]*//www\.\w+\.(com|org)[/\w]+", s):
          return True
      else:
          return False
