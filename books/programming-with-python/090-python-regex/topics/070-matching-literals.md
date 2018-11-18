title: Matching Literals
--- |

  Let's start with defining a pattern that matches `Star Wars` franchise movies. The movie names look like the following:

  ```
  Star Wars: Episode IV - A New Hope
  Star Wars: Episode V - The Empire Strikes Back
  Star Wars: Episode VI - Return of the Jedi
  ```

  Here, the pattern we are potentially looking for is `Star Wars`. It distinguishes this franchise from other movies like: `Cinderella III: A Twist in Time`, `2001: A Space Odyssey` etc. Let's test out our pattern now.

  ## Anatomy of a Regex Match

  First thing we do is import the `re` module that provides all the regex functionality in Python.

  ```Python
  >>> import re
  ```

  Next, we define our pattern.

  ```Python
  >>> REGEX_PATTERN = r"Star Wars"
  ```

  If you start the string with `r`, it marks as `Raw String Mode`. In this mode, `\` is a not a special character and need not be escaped.

  Finally, we perform the match. We use the `search(pattern, string)` function for that. As you can guess, `pattern` is the regex pattern we are searching for and `string` is the piece of text where we are searching for that pattern.

  ```Python
  >>> re.search(REGEX_PATTERN, "Star Wars: Episode I - The Phantom Menace")
  <_sre.SRE_Match object at 0x109b19bf8>
  >>> # match object was returned
  >>>
  >>> re.search(REGEX_PATTERN, "2001: A Space Odyssey")
  >>> # nothing returned
  ```

  When we search for our pattern in `Star Wars: Episode I - The Phantom Menace`, a match is found the `search()` function returns a match object that we'll discuss later. However, when we search in `2001: A Space Odyssey`, the pattern is not found and `search()` function returns `None`.

  It's an important distinction. When the pattern is found, `search()` returns a match object. But when pattern is not found, `search()` returns `None`.

  Here is the complete code for you to play around.

---
type: live-code
id: 5d6fdade-3266-4517-9ae6-fb49120541a4
code: |
  import re
  REGEX_PATTERN = r"Star Wars"

  m = re.search(REGEX_PATTERN, "Star Wars: Episode I - The Phantom Menace")
  print('Match for Star Wars...', m)

  m = re.search(REGEX_PATTERN, "2001: A Space Odyssey")
  print('Match for 2001...', m)

---
type: multiple-choice-question
id: f1de4844-1927-4b7e-a687-43ba797f1779
question: |
  Here are some movie names.  Which of these would match the regex `Window`:
options:
  - text: Rear Window
    correct: true
  - text: Secret Window
    correct: true
  - text: Open Windows
    correct: true
  - text: Win it All
  - text: Gone With The Wind

---
type: coding-question
id: 6c410957-58ab-4b59-9ebf-5b3c81ce178a
question: |
  What's the regex to select movies from Star Wars franchise?
code: |
  import re
  REGEX_PATTERN = r"..."

  def is_match(movie_name):
      if re.search(REGEX_PATTERN, movie_name):
          return True
      else:
          return False

tests: |
  assert is_match('Star Wars: The Last Jedi') == True
  assert is_match('Star Wars: The Force Awakens') == True
  assert is_match('Star Trek: Generations') == False
  assert is_match('Star Trek: First Contact') == False
  assert is_match("Empire of Dreams: The Story of the 'Star Wars' Trilogy") == False

solution: |
  import re
  REGEX_PATTERN = r"Star Wars:"

  def is_match(movie_name):
      if re.search(REGEX_PATTERN, movie_name):
          return True
      else:
          return False

---
type: coding-question
id: e1043574-1cbd-46b0-8183-815ebe1daad2
question: |
  What's the regex to select movies from Star Trek franchise?
code: |
  import re
  REGEX_PATTERN = r"..."

  def is_match(movie_name):
      if re.search(REGEX_PATTERN, movie_name):
          return True
      else:
          return False

tests: |
  assert is_match('Star Wars: The Last Jedi') == False
  assert is_match('Star Wars: The Force Awakens') == False
  assert is_match('Star Trek: Generations') == True
  assert is_match('Star Trek: First Contact') == True
  assert is_match("Empire of Dreams: The Story of the 'Star Wars' Trilogy") == False

solution: |
  import re
  REGEX_PATTERN = r"Star Trek:"

  def is_match(movie_name):
      if re.search(REGEX_PATTERN, movie_name):
          return True
      else:
          return False
