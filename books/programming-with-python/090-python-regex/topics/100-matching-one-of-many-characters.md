title: Matching One of Many Characters
--- |

  An interesting problem to solve is to match movies that mention a year in their name. Sample movie names are: `2001: A Space Odyssey`, `Dream Team 1935`, `Class of 1999` etc. To keep it simple for now, a year is four digits out of which first digit could be 1 or 2 and rest of the digits could go from 0 to 9. From what we have learnt so far, we could define a pattern like this for our purpose.

  ```Python
  REGEX_PATTERN = r"(1|2)(0|1|2|3|4|5|6|7|8|9)(0|1|2|3|4|5|6|7|8|9)(0|1|2|3|4|5|6|7|8|9)"
  ```

  Let's put it to use and see it working.

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"(1|2)(0|1|2|3|4|5|6|7|8|9)(0|1|2|3|4|5|6|7|8|9)(0|1|2|3|4|5|6|7|8|9)"
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

  The pattern works but it's quite cumbersome. Regex provides another expression that we can use here. `(0|1|2|3|4|5|6|7|8|9)` could be written as `[0123456789]`. When you put multiple characters in `[]`, regex would look for matching one of these.

  We can now rewrite the previous expression as:

  ```Python
  REGEX_PATTERN = r"[12][0123456789][0123456789][0123456789]"
  ```

  Let's try out the new pattern.

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"[12][0123456789][0123456789][0123456789]"
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

  In fact, such needs are so common that there is a further shortcut to matching digits 0-9: `[0-9]`. So, we can once again re-write the expression as `[12][0-9][0-9][0-9]`. Here is how we use it:

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"[12][0-9][0-9][0-9]"
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

  Nice. Isn't it? You can play with these variations in the following code block.

---
type: live-code
id: 4eb7e560-d86d-4eee-9f3f-3be7a381617f
code: |
  import re

  REGEX_PATTERN_1 = r"(1|2)(0|1|2|3|4|5|6|7|8|9)(0|1|2|3|4|5|6|7|8|9)(0|1|2|3|4|5|6|7|8|9)"
  REGEX_PATTERN_2 = r"[12][0123456789][0123456789][0123456789]"
  REGEX_PATTERN_3 = r"[12][0-9][0-9][0-9]"

  for PATTERN in [REGEX_PATTERN_1, REGEX_PATTERN_2, REGEX_PATTERN_3]:
      print("Trying pattern", PATTERN)
      m = re.search(PATTERN, "2001: A Space Odyssey")
      print("2001: A Space Odyssey -", m)


--- |
  ## Ranges and Alphabets

  Ranges work not only for digits but also for alphabets. So, you could say `r"[A-Z]"` to match any upper case letter, `r"[a-z]"` to match any lower case letter, `r"[A-Za-z]"` to match all English alphabet letters, `r"[A-Za-z0-9]"` to match any alphanumeric characters. In fact, you can also say `r"[AM-PZ]"` and it would match letters A, M, N, O, P, Z.

  ```Python
  >>> import re
  >>>
  >>> re.search(r"[A-Z]", "2001: A Space Odyssey")
  <_sre.SRE_Match object; span=(6, 7), match='A'>
  >>>
  >>> re.search(r"[A-Z]", "1984")
  >>>
  ```

  Here, we are looking for a movie name with an uppercase letter. The movie `2001: A Space Odyssey` is a match, whereas, the movie `1984` is not a match.


---
type: live-code
id: 4353eee6-3b93-40d9-bce4-1b84523d8a4c
code: |
  for movie_name in ["2001: A Space Odyssey", "1984"]:
      m = re.search(r"[A-Z]", movie_name)
      print(movie_name, m)
---
type: multiple-choice-question
id: 3de214bf-d472-4dfd-a05e-3552496a9394
question: |
  Here are some movie names. Which ones would match the regex `r"[0-9][0-9][0-9][0-9]:"`
options:
  - text: |
      2001: A Space Odyssey
    correct: true
  - text: |
      Amityville 1992: It's About Time
    correct: true
  - text: |
      Detroit 9000
  - text: |
      2010: The Year We Make Contact
    correct: true
  - text: |
      Godzilla 2000


---
type: multiple-choice-question
id: 50b56794-b819-4fc9-b5ab-8f7db62f3236
question: |
  Here are some movie names. Which ones would match the regex `r"[0-29][0-5][0-9][0-9]:"`
options:
  - text: |
      2001: A Space Odyssey
    correct: true
  - text: |
      Amityville 1992: It's About Time
  - text: |
      Detroit 9000
    correct: true
  - text: |
      2010: The Year We Make Contact
    correct: true
  - text: |
      Godzilla 2000
    correct: true

---
type: multiple-choice-question
id: f021d060-5ae6-4042-b6a0-87172f94be87
question: |
  From a list of movies, if we want to match the ones that are part of `Superman` or `Supergirl` franchise, which of the following regex would do the work:
options:
  - text: |
      `r"Super[mg][ai][nrl]"`
  - text: |
      `r"Super[mg][ai][nr]l"`
  - text: |
      `r"Super[mg][ai](n|rl)"`
    correct: true
  - text: |
      `r"Super[mangirl]"`

---
type: coding-question
id: c562b1db-5dd5-49dc-b821-b25dc821dcde
question: |
  Write a function `match_movie_name` that takes a movie name as input. If the movie name has at least one 4 letter word in the middle of movie name, it returns `True`. Otherwise, it returns `False`.
code: |
  # import goes here

  def match_movie_name(movie_name):
      # function code goes here

tests: |
  assert match_movie_name('Gone With The Wind') == True
  assert match_movie_name('Star Wars: The Last Jedi') == True
  assert match_movie_name('2010: the year we make contact') == True
  assert match_movie_name('Superman') == False

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r' [A-Za-z][A-Za-z][A-Za-z][A-Za-z] ', movie_name):
          return True
      else:
          return False


---
type: coding-question
id: 7ab96916-ae7b-43ba-a620-a07d017db875
question: |
  Write a function `match_movie_name` that takes a movie name as input. If the movie name has a number within a single word, return `True`. Otherwise, return `False`.
code: |
  # import goes here

  def match_movie_name(movie_name):
      # function code goes here

tests: |
  assert match_movie_name('Se7en') == True
  assert match_movie_name('Thr3e') == True
  assert match_movie_name('E=mc2') == False
  assert match_movie_name('2001: A Space Odyssey') == False
  assert match_movie_name('Superman') == False

solution: |
  import re

  def match_movie_name(movie_name):
      if re.search(r'[A-Za-z][0-9][A-Za-z]', movie_name):
          return True
      else:
          return False


---
type: coding-question
id: 7f8920cf-32e5-41d4-ba2a-01766a2b8c07
question: |
  Write a function `bat_cat_rat` which takes a movie name as input. If the movie name has any of the `bat`, `cat` or `rat` words, return `True`. Otherwise, return `False`.

code: |
  # import goes here

  def bat_cat_rat(movie_name):
      # function code goes here

tests: |
  assert bat_cat_rat('Bat Whispers') == True
  assert bat_cat_rat('Cat and Dog') == True
  assert bat_cat_rat('King Rat') == True
  assert bat_cat_rat('The Ghosts') == False

solution: |
  import re

  def bat_cat_rat(movie_name):
      if re.search(r'[BCRbcr]at', movie_name):
          return True
      else:
          return False


--- |
  ## Matching absence of characters

  Just like you can match for presence of certain characters, you can also match for their absence. `[^A-Z]` will match all characters except uppercase letters. `[^BCR]at` will match `Sat` but it will not match `Bat`, `Cat` and `Rat`. Simple trick here is to use `^`. `[BCR]` means match B, C or R but `[^BCR]` means match anything other than B, C or R.

---
type: live-code
id: abc16ed1-016c-4172-8996-c00cec99bff6
code: |
  import re
  m = re.search(r'[A-Z]', 'UPPERCASE')
  print('[A-Z] / UPPERCASE', m)

  m = re.search(r'[^A-Z]', 'UPPERCASE')
  print('[^A-Z] / UPPERCASE', m)

  m = re.search(r'[A-Z]', 'lowercase')
  print('[A-Z] / lowercase', m)

  m = re.search(r'[^A-Z]', 'lowercase')
  print('[^A-Z] / lowercase', m)


---
type: multiple-choice-question
id: 4148011c-203d-4568-90d8-d868f0bbc517
question: |
  Which of the following match regex `[0-1][0-9]:[0-6][0-9] [^P]M`:
options:
  - text: |
      04:00 AM
    correct: true
  - text: |
      11:59 AM
    correct: true
  - text: |
      06:00 PM
  - text: |
      09:23 PM

---
type: multiple-choice-question
id: 3233168c-7e35-471a-9f82-0bf10d884931
question: |
  Here are some movie names. Which ones would match the regex `[^3-9][0-5][0-9][0-9]:`
options:
  - text: |
      2001: A Space Odyssey
    correct: true
  - text: |
      Amityville 1992: It's About Time
  - text: |
      Detroit 9000
  - text: |
      2010: The Year We Make Contact
    correct: true
  - text: |
      Godzilla 2000
    correct: true
