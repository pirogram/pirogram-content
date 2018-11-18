title: Matching 0 or More Occurrences
--- |

  `*` stands for `{0,}` which means at least 0 and at most infinite matches. `BA*T` would match `BT`, `BAT`, `BAAAAAAAAAAAAAAAAAAAAAT` etc.

  ```Python
  >>> import re
  >>>
  >>> re.search( "BA*T", "BT")
  <_sre.SRE_Match object; span=(0, 2), match='BT'>
  >>>
  >>> re.search( "BA*T", "BAT")
  <_sre.SRE_Match object; span=(0, 3), match='BAT'>
  >>>
  >>> re.search( "BA*T", "BAAAAAT")
  <_sre.SRE_Match object; span=(0, 7), match='BAAAAAT'>
  ```

---
type: multiple-choice-question
id: 14376373-e7c1-494e-a8f2-531f565e2bf7
question: |
  Which of the following would match regex `\w\s*:\s*\w`:
options:
  - text: "Potatoes: 4"
    correct: true
  - text: "Potatoes:4"
    correct: true
  - text: "Potatoes    :     4"
    correct: true
  - text: "4: Potatoes"
    correct: true
  - text: "Potatoes ~::~ 4"
  - text: ":Potatoes:"

---
type: coding-question
id: dc76c54b-5968-4a3b-a02f-260a10651451
question: |
  Write a function `match_url` that takes a url as input. It returns `True` if the url is of type http (`http://`) or https (`https://`) AND the url domain is .com or .org. Otherwise, it returns `False`.

code: |
  # import goes here

  def match_url(url):
      # code goes here

tests: |
  assert match_url('https://www.google.com') == True
  assert match_url('http://yahoo.org') == True
  assert match_url('http://www.facebook.com/profile') == True
  assert match_url('http://www.wattpad.com/tags/fiction') == True
  assert match_url('ftp://www.google.com') == False
  assert match_url('http://www.yahoo.net') == False
  assert match_url('https://www.facebook.com') == True
  assert match_url('https://www.photo.net') == False

solution: |
  import re

  def match_url(url):
      if re.search(r"https?://.*\.(org|com)", url):
          return True
      else:
          return False

---
type: coding-question
id: dba74cbc-9b45-4215-8603-2f519c3d0bae
question: |
  Write a function `match_sentence` that takes a string as input. It returns `True` if the string has word `cat` followed by `dog`. Otherwise, it returns `False`. Hint: use repetition of `.` to match word & space characters.

code: |
  # import goes here

  def match_sentence(s):
      # code goes here

tests: |
  assert match_sentence('The cat chased the dog.') == True
  assert match_sentence('The cat ran away from the dog.') == True
  assert match_sentence('The dog looked at the cat with confusion.') == False
  assert match_sentence('The dog was friendly to the cat.') == False
  assert match_sentence('The cat drank milk.') == False

solution: |
  import re

  def match_sentence(s):
      if re.search(r"cat.*dog", s):
          return True
      else:
          return False

---
type: coding-question
id: 5ee02aed-22c0-48de-a012-f393b69c9bee
question: |
  Write a function `match_sentence` that takes a string as input. It returns `True` if the string has word `cat` followed by `dog` or vice versa (i.e. `dog` followed by `cat`). Otherwise, it returns `False`.

code: |
  # import goes here

  def match_sentence(s):
      # code goes here

tests: |
  assert match_sentence('The cat chased the dog.') == True
  assert match_sentence('The cat ran away from the dog.') == True
  assert match_sentence('The dog looked at the cat with confusion.') == True
  assert match_sentence('The dog was friendly to the cat.') == True
  assert match_sentence('The cat drank milk.') == False

solution: |
  import re

  def match_sentence(s):
      if re.search(r"(cat.*dog|dog.*cat)", s):
          return True
      else:
          return False
