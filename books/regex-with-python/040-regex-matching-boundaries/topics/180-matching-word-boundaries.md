title: Matching Word Boundaries
--- |
  In regex, `\b` matches word boundary. What does it mean? Let's first define what a word is.

  In regex, a word is an unbroken sequence of `[A-Za-z0-9_]` or `\w`. The sentence `cat jumped` has two words: `cat` and `jumped`. OTOH, `key:value` has two words: `key` and `value`. Even `http-proto` has two words: `http` and `proto`.

  Symbol `\b` matches at the start and end of word boundary. The regex `\bcat\b` would match sentences that have word `cat`. Let's give it a try:

  ```Python
  >>> import re
  >>> REGEX_PATTERN = r"\bcat\b"
  >>>
  >>> re.search(REGEX_PATTERN, "cat is fat")
  <_sre.SRE_Match object; span=(0, 3), match='cat'>
  >>>
  >>> re.search(REGEX_PATTERN, "the cat jumped over the wall.")
  <_sre.SRE_Match object; span=(4, 7), match='cat'>
  >>>
  >>> re.search(REGEX_PATTERN, "this is my cat.")
  <_sre.SRE_Match object; span=(11, 14), match='cat'>
  >>>
  >>> re.search(REGEX_PATTERN, "he was herding the cattle.")
  >>>
  >>> re.search(REGEX_PATTERN, "this muscat is funny.")
  >>>
  ```

---
type: multiple-choice-question
id: 66532415-dbad-42db-8664-17bb962fd21c
question: |
  How many words (as per regex definition) are there in `http://www.google.com/search`?

options:
  - text: "3"
  - text: "4"
  - text: "5"
    correct: true
  - text: "6"

---
type: coding-question
id: 67d4ece9-9a4b-4f0e-b733-5ced60ce9bb8
question: |
  Write a function `mentions_dog` that takes a string as input. It returns `True` if the string mentions animal dog. Otherwise, it returns `False`.

code: |
  # import goes here

  def mentions_dog(s):
      # code goes here

tests: |
  assert mentions_dog('a dog was barking.') == True
  assert mentions_dog('dog is a loyal animal.') == True
  assert mentions_dog('this is my dog.') == True
  assert mentions_dog('is it a dogfish?') == False
  assert mentions_dog('dogfood is about using your own software.') == False

solution: |
  import re

  def mentions_dog(s):
      if re.search(r"\bdog\b", s):
          return True
      else:
          return False

---
type: coding-question
id: de6b8d33-1db6-4bd4-92dc-51856f2eb37b
question: |
  Write a function `match_sentence` that takes a string as input. It returns `True` if there is at least one word with exactly 5 letters. Otherwise, it returns `False`.

code: |
  # import goes here

  def match_sentence(s):
      # code goes here

tests: |
  assert match_sentence('I am a super human.') == True
  assert match_sentence('Spice route is not spicy.') == True
  assert match_sentence('Cat cannot climb.') == True
  assert match_sentence('Spiderman returns is not interesting.') == False
  assert match_sentence('Cat can jump.') == False

solution: |
  import re

  def match_sentence(s):
      if re.search(r"\b\w{5}\b", s):
          return True
      else:
          return False

---
type: coding-question
id: 584051c2-5cb3-444c-819c-8da6333804a0
question: |
  Write a function `match_sentence` that takes a string as input. It returns `True` if there is a year in 4 digit format. Otherwise, it returns `False`.

code: |
  # import goes here

  def match_sentence(s):
      # code goes here

tests: |
  assert match_sentence('In year 2000, there was an earthquake.') == True
  assert match_sentence('1984.') == True
  assert match_sentence("In 2020, I'll be 20 years old") == True
  assert match_sentence('I am 20 years old now.') == False
  assert match_sentence('123456789 is a really long number.') == False

solution: |
  import re

  def match_sentence(s):
      if re.search(r"\b\d{4}\b", s):
          return True
      else:
          return False
