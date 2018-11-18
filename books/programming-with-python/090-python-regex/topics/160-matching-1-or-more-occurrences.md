title: Matching 1 or More Occurrences
--- |

  `+` stands for `{1,}` which matches at least 1 and at most infinite times.

  How do you match the movies with at least 2 words in their name? `\w+\s+\w+` would do the trick. Let's give it a try.

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"\w+\s+\w+"
  >>>
  >>> re.search(REGEX_PATTERN, "Spiderman Returns")
  <_sre.SRE_Match object; span=(0, 17), match='Spiderman Returns'>
  >>>
  >>> re.search(REGEX_PATTERN, "Spiderman")
  >>>
  ```

---
type: coding-question
id: 3cacba35-8a65-4acb-b1fc-1cf375c8b55c
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie has at least three words. Otherwise, it returns `False`.

code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Gone With The Wind') == True
  assert match_movie_name('Superman') == False
  assert match_movie_name('La La Land') == True
  assert match_movie_name('The Sixth Sense') == True
  assert match_movie_name('Braveheart') == False

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r"\w+\s\w+\s\w+", movie_name):
          return True
      else:
          return False

---
type: coding-question
id: d5ee27df-3581-4b7e-aa2d-354be285db74
question: |
  Write a function `match_movie_name` that takes a movie name as input. It returns `True` if the movie has at least three words. Otherwise, it returns `False`.

  Note: you have to match `:` as part of characters between words. Hint: you can use `[]` or `|` for matching characters between words.

code: |
  # import goes here

  def match_movie_name(movie_name):
      # code goes here

tests: |
  assert match_movie_name('Gone With The Wind') == True
  assert match_movie_name('Superman') == False
  assert match_movie_name('Star Wars: The Last Jedi') == True
  assert match_movie_name('2010: the year we make contact') == True
  assert match_movie_name('Braveheart') == False

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r"\w+[\s:]+\w+[\s:]+\w+[\s:]+\w+", movie_name):
          return True
      else:
          return False

---
type: coding-question
id: 20698e4a-4f06-4eec-adc7-8c69cac3808b
question: |
  Write a function `match_sentence` that takes a string as input. It returns `True` if the string has two years. Otherwise, it returns `False`.

code: |
  # import goes here

  def match_sentence(s):
      # code goes here

tests: |
  assert match_sentence('1984 comes before 1999.') == True
  assert match_sentence('In 2015, I bought 2 cars.') == False
  assert match_sentence('2004 comes after 2001.') == True
  assert match_sentence('There was a flood in 1999.') == False
  assert match_sentence('12345678 is a long number.') == False

solution: |
  import re

  def match_sentence(s):
      if re.search(r"\d{4}.+\d{4}", s):
          return True
      else:
          return False
