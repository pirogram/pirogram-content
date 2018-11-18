title: Custom Comparison
--- |
  Consider the following example for sorting:

---
type: live-code
id: 2079d3a6-01b8-4cb7-a96a-50ea4de95673
code: |
  fruits = ['Banana', 'apple', 'Kiwi', 'pineapple', 'orange']
  sorted(fruits)

--- |
  What if we want the sorting to be case-insensitive? That's where `key` arguments comes in.

---
type: live-code
id: beb2db0e-e79d-4179-a021-7cc3251c8c09
code: |
  fruits = ['Banana', 'apple', 'Kiwi', 'pineapple', 'orange']
  sorted(fruits, key=str.lower)

--- |
  Instead of comparing the items as they are (i.e. `Banana` with `apple`), the items would be first passed to `str.lower()` function and the output value of that function would be compared (i.e. `banana` with `apple`).

  Another example: sort the list of words based on the length of the words. Smaller words come first and longer words come later.

---
type: live-code
id: 59478811-0593-478e-b5e1-668be8783c05
code: |
  words = 'No legacy is so rich as honesty'.split()

  sorted(words, key=len)

--- |
  We can pass even our own functions as argument to `key`. Let's say, we want to sort a list of words by the number of vowels in the word.

---
type: live-code
id: e1c8c63e-e1d9-47dc-a255-db7128860435
code: |
  def vowels_count(s):
    s = s.lower()
    return s.count('a') + s.count('e') + s.count('i') \
      + s.count('o') + s.count('u')

  words = 'A fool thinks of himself as wise but a wise man thinks of himself to be a fool'.split()

  sorted(words, key=vowels_count)

---
type: testless-coding-question
id: 331b64c5-ee81-4176-939b-d93cd0b2f804
question: |
  Given a list of words, sort them by the number of times letter `a` occurs in the words. For example, input `['a', 'word', 'apart']` should return `['word', 'a', 'apart']`.

  Note: you'll need to write a custom function as `key` argument to `sorted()`.
code: |
  words = ['a', 'word', 'apart']

  # your code goes here

---
type: testless-coding-question
id: e23e5e54-8a28-45c6-81a1-d76da08d87c6
question: |
  Given a list of lists, sort them by the number of items in the embedded list. For example, given the following list:
  ```
  [ [1], [1, 2, 3], [1, 2] ]
  ```
  the resulting list should be:
  ```
  [ [1], [1, 2], [1, 2, 3] ]
  ```
code: |
  list_of_lists = [
    [1, 2, 3, 4],
    [1, 2],
    [1],
    [1, 2, 3]
  ]

  # your code goes here
---
type: testless-coding-question
id: 17a3df2a-8ffb-4f5f-a7db-d7bc69093f07
question: |
  Given a list of sentences, sort them by the number of words in them.
code: |
  sentences = [
    "Everyone needs a little inspiration from time to time",
    "Get busy living or get busy dying",
    "Great minds discuss ideas; average minds discuss events; small minds discuss people",
    "Do not cry because it is over, smile because it happened",
    "Be yourself; everyone else is already taken"
  ]

  # your code goes here

---
type: testless-coding-question
id: 6221c1a2-fdbd-4b39-99ff-2d1c6fa82343
question: |
  Given a list of words, sort them by number of consonants in the words.
code: |
  words = 'Everyone needs a little inspiration from time to time'.split()

  # your code goes here

---
type: testless-coding-question
id: 6a3bf50a-6232-4e37-b6a9-62f06238647b
question: |
  Given a list of words, sort them by vowel density (i.e. number of vowels in the word divided by number of letters in the word).
code: |
  words = 'Everyone needs a little inspiration from time to time'.split()

  # your code goes here
