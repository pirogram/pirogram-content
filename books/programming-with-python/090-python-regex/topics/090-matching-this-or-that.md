title: Matching This or That
--- |

  We'll now solve the problem of matching movie names that could be from `Star Wars` or `Star Trek` franchise. So, the regex pattern should match the following:

  ```
  Star Wars: Episode I - The Phantom Menace
  Star Wars: Episode II - Attack of the Clones
  Star Trek: Generations
  Star Trek: First Contact
  ```

  But it should not match the following:

  ```
  Stardust
  Star 80
  Star of Midnight
  ```

  In regex, multiple patterns can be combined with `|` which means `OR` condition. For example, to solve our current problem, we could define the pattern as `Star Wars:|Star Trek:`. This pattern would match either `Star Wars:` or `Star Trek:`. Let's give it a try.

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"Star Wars:|Star Trek:"
  >>>
  >>> re.search(REGEX_PATTERN, "Star Wars: Episode I - The Phantom Menace")
  <_sre.SRE_Match object at 0x109b19c60>
  >>>
  >>> re.search(REGEX_PATTERN, "Star Trek: Generations")
  <_sre.SRE_Match object at 0x109b19bf8>
  >>>
  >>> re.search(REGEX_PATTERN, "Stardust")
  >>> re.search(REGEX_PATTERN, "Star 80")
  >>> # Stardust and Star 80 don't match the pattern.
  ```

  The regex `Star Wars:|Star Trek:` has multiple duplicate elements. We can make it more concise with `Star (Wars|Trek):`. It means look for `Star`, followed by a space followed by either `Wars` or `Trek`, followed by a `:`. Let's give it a try:

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"Star (Wars|Trek):"
  >>>
  >>> re.search(REGEX_PATTERN, "Star Wars: Episode I - The Phantom Menace")
  <_sre.SRE_Match object at 0x109b19c60>
  >>>
  >>> re.search(REGEX_PATTERN, "Star Trek: Generations")
  <_sre.SRE_Match object at 0x109b19bf8>
  >>>
  >>> re.search(REGEX_PATTERN, "Stardust")
  >>> re.search(REGEX_PATTERN, "Star 80")
  >>> # Stardust and Star 80 don't match the pattern.
  ```

---
type: multiple-choice-question
id: 2b151f26-94fd-4932-bab8-349427ce848d
question: |
  Here are some movie names. Which of these would match the regex `Force|Jedi`:
options:
  - text: |
      Star Wars: The Last Jedi
    correct: true
  - text: |
      Star Wars: The Force Awakens
    correct: true
  - text: |
      Star Trek: Discovery
  - text: |
      Star Trek: Voyager

---
type: coding-question
id: 4007c758-69cf-46a6-928e-4b7cd55bf4fd
question: |
  Write a function `is_starry_movie` that takes a movie name as input. It returns `True` if the movie is from `Star Wars` or `Star Trek` franchise. Otherwise, it returns `False`.

code: |
  # your imports go here.

  def is_starry_movie(movie_name):
      # function code goes here.

tests: |
  assert is_starry_movie('Star Wars: The Last Jedi') == True
  assert is_starry_movie('Star Wars: The Force Awakens') == True
  assert is_starry_movie('Star Trek: Discovery') == True
  assert is_starry_movie('Star Trek: Voyager') == True
  assert is_starry_movie('2001: A Space Odyssey') == False
  assert is_starry_movie('Star Dust') == False

solution: |
  import re

  def is_starry_movie(movie_name):
      if re.search(r"Star (Wars|Trek):", movie_name):
          return True
      else:
          return False

---
type: multiple-choice-question
id: fa5b08c2-b54d-4547-9a6d-eb4ff46f2b4c
question: |
  From a list of movies, if we want to match the ones that are part of `Superman` or `Supergirl` franchise, which of the following regex would do the work:
options:
  - text: |
      `Superman|Supergirl`
    correct: true
  - text: |
      `Super(man|girl)`
    correct: true
  - text: |
      `Super(m|g)(a|i)(n|r)l`
  - text: |
      `Super(m|g)(a|i)(n|rl)`
    correct: true
  - text: |
      `Super((man|girl))`
    correct: true
  - text: |
      `Super((man)|girl)`
    correct: true

---
type: multiple-choice-question
id: a16209cb-a012-4ce5-8f0a-d30ffbaa3a5c
question: |
  Which of the following movies will be matched by regex `(Star (Wars|Trek):)|(Super(man|girl))`
options:
  - text: |
      Star Wars: The Last Jedi
    correct: true
  - text: |
      2001: A Space Odyssey
  - text: |
      Star Dust
  - text: |
      Star Trek: Voyager
    correct: true
  - text: |
      Superman Returns
    correct: true
  - text: |
      Supergirl
    correct: true

---
type: coding-question
id: 9cb8a852-cfbd-491b-af75-47edc4c229a9
question: |
  Write a function `is_spacey_movie` that takes a movie name as input. It returns `True` for all movies that match Star Wars, Star Trek or Space. Otherwise, it returns `False`.
code: |
  # imports go here

  # function goes here.

tests: |
  assert is_spacey_movie('Star Wars: The Last Jedi') == True
  assert is_spacey_movie('2001: A Space Odyssey') == True
  assert is_spacey_movie('Star Dust') == False
  assert is_spacey_movie('Star Trek: Voyager') == True
  assert is_spacey_movie('Superman') == False
  assert is_spacey_movie('Alien Space Avenger') == True

solution: |
  import re

  def is_spacey_movie(movie_name):
      if re.search(r"(Space|Star (Wars|Trek))", movie_name):
          return True
      else:
          return False
