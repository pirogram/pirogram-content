title: Matching Character Types
--- |

  Let's revisit the problem of identifying movies that have a year in their name. We looked at set of characters (i.e. `[0-9]`) as a solution. Some of these sets are so commonly used that there are special symbols for them. These symbols are:

  * `\w` is equivalent to `[A-Za-z0-9_]`
  * `\W` is opposite of `\w` i.e. `[^A-Za-z0-9_]`
  * `\s` is equivalent to `[ \t\r\n]`
  * `\S` is opposite of `\s` i.e. `[^ \t\r\n]`
  * `\d` is equivalent to `[0-9]`
  * `\D` is opposite of `\d` i.e. `[^0-9]`
  * `.` is the most interesting shortcut and it matches all characters without exception.

  So, we had earlier used regex `[12][0-9][0-9][0-9]` to find movies with a year in their name. This regex could also be written as `[12]\d\d\d`. In this, `\d` stands for a digit. Let's give it a try:

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"[12]\d\d\d"
  >>>
  >>> re.search(REGEX_PATTERN, "2001: A Space Odyssey")
  <_sre.SRE_Match object; span=(0, 4), match='2001'>
  >>>
  >>> re.search(REGEX_PATTERN, "Dream Team 1935")
  <_sre.SRE_Match object; span=(11, 15), match='1935'>
  >>>
  >>> re.search(REGEX_PATTERN, "Superman")
  >>>
  ```

  Similarly, let's say if we want to find out if a movie name has at least 1 word that is five letters long (or even longer). Instead of writing `[A-Za-z][A-Za-z][A-Za-z][A-Za-z][A-Za-z]`, we could write `\w\w\w\w\w`. The `\w` based regex is more concise and readable. Here it is in action:

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"\w\w\w\w\w"
  >>>
  >>> re.search(REGEX_PATTERN, "Dream Team 1995")
  <_sre.SRE_Match object; span=(0, 5), match='Dream'>
  >>>
  >>> re.search(REGEX_PATTERN, "Superman")
  <_sre.SRE_Match object; span=(0, 5), match='Super'>
  >>>
  >>> re.search(REGEX_PATTERN, "Cat And Dog")
  >>>
  ```

  What if we want to find out movies whose name is at least 6 letter long? The regex `......` will do the trick for us:

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"......"
  >>>
  >>> re.search(REGEX_PATTERN, "Superman")
  <_sre.SRE_Match object; span=(0, 6), match='Superm'>
  >>>
  >>> re.search(REGEX_PATTERN, "1984")
  >>>
  ```

  Expression `r"\w\w\w\w\s\w\w\w\w"` would match a movie name that has at least two words and both the words have at least 4 letters.

  ```Python
  >>> re.search(r"\w\w\w\w\s\w\w\w\w", "Gone With The Wind")
  <_sre.SRE_Match object; span=(0, 9), match='Gone With'>
  >>>
  >>> re.search(r"\w\w\w\w\s\w\w\w\w", "The Ghosts")
  >>>
  >>> re.search(r"\w\w\w\w\s\w\w\w\w", "Cat And Dog")
  >>>
  ```

---
type: coding-question
id: 2b4d6694-3281-4d0a-b663-a9f089f7a081
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie has at least 8 characters in the name. Otherwise, it returns `False`.
code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Se7en') == False
  assert match_movie_name('Thr3e') == False
  assert match_movie_name('E=mc2') == False
  assert match_movie_name('2001: A Space Odyssey') == True
  assert match_movie_name('Superman') == True

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r"........", movie_name):
          return True
      else:
          return False


---
type: coding-question
id: a1c91f6f-0aa9-48b2-9f36-fb20beba582b
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
      if re.search(r"\w\w\w\w\s\w\w\w\w", movie_name):
          return True
      else:
          return False



---
type: coding-question
id: cd83f62d-4944-4a63-af26-98da4fbd50b9
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
      if re.search(r"(\w\w\w\w\s\w\w\w\w|\w\w\w\s\w\w\w\w)", movie_name):
          return True
      else:
          return False

---
type: coding-question
id: bccd002e-ecfa-4006-bf3f-3d404c607381
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie has a number surrounded by one letter on each side. Otherwise, it returns `False`.

code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Se7en') == True
  assert match_movie_name('Thr3e') == True
  assert match_movie_name('E=mc2') == False
  assert match_movie_name('2001: A Space Odyssey') == False
  assert match_movie_name('Superman') == False

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r"\w\d\w", movie_name):
          return True
      else:
          return False

---
type: coding-question
id: 08dbdec3-eb4a-492f-9548-ff7e5c1e7b5b
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie has two consecutive non-word letters (Hint: use `\W`). Otherwise, it returns `False`.

code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Star Wars: Return of the Jedi') == True
  assert match_movie_name('Star Trek: Voyager') == True
  assert match_movie_name('Erkan & Stefan 2') == True
  assert match_movie_name('Cat And Dog') == False
  assert match_movie_name('Alice in Wonderland') == False

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r"\w\d\w", movie_name):
          return True
      else:
          return False
