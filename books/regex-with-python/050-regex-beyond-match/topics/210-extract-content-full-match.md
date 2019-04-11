title: Extract Full Match
--- |

  Let's revisit the problem of identifying year in a movie name. We created regex `\b\d{4}\b` and it matches `2009: Lost Memories` but not `Superman`. What if you want to solve a slightly differnet problem. Not only that you want to find out if a movie name has year, but also which year it is. Let's step through the code for this line by line.

  First, you import the `re` module:

  ```Python
  >>> import re
  ```

  Next, you search for the regex in movie name. This time, you store the return value in a variable.

  ```Python
  >>> match = re.search(r"\b\d{4}\b", "2009: Lost Memories")
  ```

  Finally, `match.group()` would give you the piece of text that matched your regex:

  ```Python
  >>> match.group()
  '2009'
  ```

  You can play with the code here:

---
type: live-code
id: 12a12b5c-7dc4-4bfc-9834-e4132e122ad0
code: |
  import re

  match = re.search(r"\b\d{4}\b", "2009: Lost Memories")

  print(match.group())

--- |

  You should refer to the documentation of [Match Object](https://docs.python.org/3/library/re.html#match-objects) on Python documentation.

---
type: coding-question
id: 1fb6bc2e-29b5-41a9-83e4-9f39dd92aa68
question: |
  Write a function `first_five_letter_word` that takes a string as input. If the string starts with a five letter word, the function returns that word. Otherwise, it returns `None`.

code: |
  # import goes here

  def first_five_letter_word(s):
      # code goes here

tests: |
  assert first_five_letter_word('Sense and Sensibility') == 'Sense'
  assert first_five_letter_word('Gumby: The Movie') == 'Gumby'
  assert first_five_letter_word("Jason's Lyric") == 'Jason'
  assert first_five_letter_word('Superman') == None
  assert first_five_letter_word('2009: Lost Memories') == None
  assert first_five_letter_word('Sensibility and Sense') == None

solution: |
  import re

  def first_five_letter_word(s):
      match = re.search(r"^\w{5}\b", s)
      if not match:
          return None

      return match.group()

---
type: coding-question
id: f006ebc6-89b8-4171-9d63-bc6f8f7f5835
question: |
  Write a function `extract_adverb` that takes a string as input. If the string has an adverb (strictly, deadly, objectively etc) , the function returns that adverb. Otherwise, it returns `None`.

code: |
  # import goes here

  def extract_adverb(s):
      # code goes here

tests: |
  assert extract_adverb('Strictly Ballroom') == 'Sense'
  assert extract_adverb('Tough and Deadly') == 'Gumby'
  assert extract_adverb('Heavenly Creatures') == 'Jason'
  assert extract_adverb('Superman') == None

solution: |
  import re

  def extract_adverb(s):
      match = re.search(r"\b\w+ly\b", s)
      if not match:
          return None

      return match.group()

---
type: coding-question
id: 42f6e7f4-8066-4422-81dd-7d18cb81298a
question: |
  Write a function `extract_email` that takes a string as input. If the string has an email address, the function returns that. Otherwise, it returns `None`.

code: |
  # import goes here

  def extract_email(s):
      # code goes here

tests: |
  assert extract_email('smith@yahoo.com - Steve Smith') == 'smith@yahoo.com'
  assert extract_email('hi@turtleprogrammer.com - Turtle') == 'hi@turtleprogrammer.com'
  assert extract_email('rama@gmail.com') == 'rama@gmail.com'
  assert extract_email('Superman') == None
  assert extract_email('rama @gmail.com') == None

solution: |
  import re

  def extract_email(s):
      match = re.search(r"\b\w+@[\w-]+\.com\b", s)
      if not match:
          return None

      return match.group()
