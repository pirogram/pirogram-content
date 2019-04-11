title: Matching m To n Occurrences
--- |
  In regex, the general purpose method of matching certain number of occurrences is to use `{m,n}`. `\d{2,4}` would match at least 2 and at most 4 occurrences of `\d`.

  Earlier, we wrote the regex `\d\d\d\d` for matching a year in movie name. The same could be re-written as `\d{4,4}` which matches at least 4 and at most 4 occurrences of `\d`. It could be further shortened to `\d{4}`.

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"\d{4}"
  >>>
  >>> re.search(REGEX_PATTERN, "2001: A Space Odyssey")
  <_sre.SRE_Match object; span=(0, 4), match='2001'>
  >>>
  >>> re.search(REGEX_PATTERN, "Amityville 1992: It's About Time")
  <_sre.SRE_Match object; span=(11, 15), match='1992'>
  >>>
  >>> re.search(REGEX_PATTERN, "Gone With The Wind")
  >>>
  >>> re.search(REGEX_PATTERN, "E=mc2")
  >>>
  ```
---
type: coding-question
id: 2e62b6a3-6843-446e-b199-b2cff2277ead
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie has at least 12 characters in the name (hint: use `{}`). Otherwise, it returns `False`.

code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Se7en') == False
  assert match_movie_name('Superman') == False
  assert match_movie_name('Spiderman Returns') == True
  assert match_movie_name('2001: A Space Odyssey') == True
  assert match_movie_name('Star Wars: Return of the Jedi') == True

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r".{12,}", movie_name):
          return True
      else:
          return False
--- |

  Let's look at a different problem this time. You want to match numbers 0 to 999. How would you do that? `\d{1,3}` would do the trick.

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"\d{1,3}"
  >>>
  >>> re.search(REGEX_PATTERN, "8")
  <_sre.SRE_Match object; span=(0, 1), match='8'>
  >>> # Matches 1 \d because only 1 is available.
  >>>
  >>> re.search(REGEX_PATTERN, "64")
  <_sre.SRE_Match object; span=(0, 2), match='64'>
  >>> # Matches 2 \d because only 2 are available.
  >>>
  >>> re.search(REGEX_PATTERN, "256")
  <_sre.SRE_Match object; span=(0, 3), match='256'>
  >>> # Matches 3 \d because all three are available.
  >>>
  >>> re.search(REGEX_PATTERN, "1024")
  <_sre.SRE_Match object; span=(0, 3), match='102'>
  >>> # Matches 3 \d and stops looking for more.
  >>>
  >>> re.search(REGEX_PATTERN, "abcdef")
  >>> # Not even 1 \d found. So, not a match.
  ```

  Let's re-work some of the older problems but this time, make use of `{}` operators to specify number of occurrences.

---
type: multiple-choice-question
id: 4b2aa2ca-eca9-4721-9a87-fa67219966ad
question: |
  Which of the following would match regex `[+-]\d{1,2}`
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
id: f8f71c16-f771-4ed5-afeb-43858df03a07
question: |
  Write a function `match_number` that takes a string as input. It returns `True` if the string matches numbers -999 to 999. Otherwise, it returns `False`.

  So, it should match -999, -998, …, 998, 999. Use the `{m,n}` convention to specify occurrences. Hint: `-` has 0 to 1 occurrence while `\d` has 1 to 3 occurrences.

code: |
  # import goes here

  def match_number(s):
      # code goes here

tests: |
  assert match_number('-733') == True
  assert match_number('4') == True
  assert match_number('3') == True
  assert match_number('AB') == False
  assert match_number('DEF') == False

solution: |
  import re

  def match_number(s):
      if re.search(r"-{0,1}\d{1,3}", s):
          return True
      else:
          return False


---
type: coding-question
id: 123cc9d9-c4a1-43c4-9394-225b1ab1d76f
question: |
  Write a function `match_number` that takes a string as input. It returns `True` if the string matches numbers -999 to 999. The positive numbers could be prefixed with `+` (e.g. 97 and +97 are valid). Otherwise, it returns `False`.

  So, it should match -999, -998, …, 998, 999. Use the `{m,n}` convention to specify occurrences. Hint: in this case, `[+-]` have 0 to 1 occurrence and `\d` has 1 to 3

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
      if re.search(r"[-+]{0,1}\d{1,3}", s):
          return True
      else:
          return False


---
type: coding-question
id: cf65ce5a-a047-400f-a31a-a33629f832ab
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie has a word which is at least 4 letter long followed by another word which is at least 3 letter long. Otherwise, it returns `False`.

code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Bat Whispers') == False
  assert match_movie_name('Cat and Dog') == False
  assert match_movie_name('King Rat') == True
  assert match_movie_name('The Ghosts') == False

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r"\w{4,}\s\w{3,}", movie_name):
          return True
      else:
          return False

---
type: coding-question
id: 10edf34a-f317-42ca-98a0-cb1d6995c7c8
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie has a word which is at least 4 letter long followed by another word which is at least 3 letter long or vice versa (i.e. a 3 letter long word is followed by a 4 letter long word). Otherwise, it returns `False`.

code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Bat Whispers') == True
  assert match_movie_name('Cat and Dog') == False
  assert match_movie_name('King Rat') == True
  assert match_movie_name('The Ghosts') == True

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r"(\w{4,}\s\w{3,}|\w{3,}\s\w{4,})", movie_name):
          return True
      else:
          return False

--- |
  ## m To n Roundup

  `{m,n}` has four variations:

  * `{m,n}` matches at least m and at most n occurrences.
  * `{m}` matches exactly m occurrences.
  * `{m,}` matches at least m occurrneces (no upper bound).
  * `{,n}` matches at least 0 and at most n occurrences.
