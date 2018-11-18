title: Matching Special Characters
--- |

  Some characters have special meaning in regex (e.g. `.`, `?`, `(`, `)`, `*`, `+`, `^`, `$`, `\`, `[`, `]`) . We'll look at their use later in the game. For now, suffice it to say that if you want to match any of these, you have to precede them with `\` to find a match. For example, if you want to match movie names that have a full stop, you have to use `\.` as regex pattern and not `.`.

  Let's solve the problem of matching movie names that have a full stop. Here is the wrong pattern:

  ```Python
  >>> import re
  >>> INCORRECT_REGEX_PATTERN = r'.'
  >>>
  >>> re.search(INCORRECT_REGEX_PATTERN, 'Mr. Average')
  <_sre.SRE_Match object at 0x109b19bf8>
  >>>
  >>> re.search(INCORRECT_REGEX_PATTERN, 'Stardust')
  <_sre.SRE_Match object at 0x109b19c60>
  >>> # should not have matched Stardust but it did.
  ```

  Here is the same exercise with the right regex pattern:

  ```Python
  >>> import re
  >>> CORRECT_REGEX_PATTERN = r'\.'
  >>>
  >>> re.search(CORRECT_REGEX_PATTERN, 'Mr. Average')
  <_sre.SRE_Match object at 0x109b19bf8>
  >>>
  >>> re.search(CORRECT_REGEX_PATTERN, 'Stardust')
  >>> # did not match Stardust
  ```

---
type: coding-question
id: ffb4f681-4808-439c-bb43-23727c19e013
question: |
  Write a function `has_dot` that takes a movie name as input. It should return `True` if the movie name has `.` character. Otherwise, it should return `False`.

code: |
  import re

  def has_dot(movie_name):
      # Your code goes here.

tests: |
  assert has_dot('Mr. Pip') == True
  assert has_dot('The D.I.') == True
  assert has_dot('Stardust') == False
  assert has_dot('Superman') == False

solution: |
  import re

  def has_dot(movie_name):
      if re.search(r'\.', movie_name):
          return True
      else:
          return False
