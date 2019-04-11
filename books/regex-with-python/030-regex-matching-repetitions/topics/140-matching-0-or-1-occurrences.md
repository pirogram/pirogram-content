title: Matching 0 or 1 Occurrences
--- |

  `?` stands for `{0,1}`. A pattern should match at least 0 and at most 1 time. Effectively, it's another way of saying that the pattern may or may not be there. It's used very frequently.

  Let's revisit the problem of matching numbers from -9 to 9. Also, 7 could be written as 7 as well as +7. We could re-write the previous regex (`[+-]{0,1}\d`) as `[+-]?\d`. Let's give it a try:

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"[+-]?\d"
  >>>
  >>> re.search(REGEX_PATTERN, "-7")
  <_sre.SRE_Match object; span=(0, 2), match='-7'>
  >>>
  >>> re.search(REGEX_PATTERN, "7")
  <_sre.SRE_Match object; span=(0, 1), match='7'>
  >>> re.search(REGEX_PATTERN, "+7")
  >>>
  <_sre.SRE_Match object; span=(0, 2), match='+7'>
  >>>
  ```

---
type: multiple-choice-question
id: c1e4f09c-8569-4d35-aac9-018ff5b6cfaa
question: |
  Which of the following would match regex `[+-]\d?\d`

options:
  - text: "+40"
    correct: true
  - text: "-2"
    correct: true
  - text: "+324"
    correct: true
  - text: "22"

---
type: coding-question
id: 62aeb766-20d9-4021-a140-618342d4ff16
question: |
  Write a function `match_number` that takes a string as input. It returns `True` if the string matches numbers -999 to 999. The positive numbers could be prefixed with `+` (e.g. 97 and +97 are valid). Otherwise, it returns `False`.

  So, it should match -999, -998, …, 998, 999. Use `?` in the regex.

code: |
  # import goes here

  def match_number(s):
      # code goes here

tests: |
  assert match_number('-733') == True
  assert match_number('4') == True
  assert match_number('3') == True
  assert match_number('+42') == True
  assert match_number('AB') == False
  assert match_number('DEF') == False

solution: |
  import re

  def match_number(s):
      if re.search(r"[-+]?\d{1,2}", s):
          return True
      else:
          return False

---
type: coding-question
id: ae9c9584-2889-44ff-95f3-f9fa831a0e31
question: |
  Write a function `match_url` that takes a url as input. It returns `True` if the url is of type http (`http://`) or https (`https://`). Otherwise, it returns `False`.

code: |
  # import goes here

  def match_url(url):
      # code goes here

tests: |
  assert match_url('https://www.google.com') == True
  assert match_url('http://www.google.com') == True
  assert match_url('https://www.yahoo.com') == True
  assert match_url('http://www.yahoo.com') == True
  assert match_url('ftp://www.google.com') == False
  assert match_url('scp://www.yahoo.com') == False
  assert match_url('http-proto') == False
  assert match_url('https is a protocol') == False

solution: |
  import re

  def match_url(url):
      if re.search(r"https?://", url):
          return True
      else:
          return False
