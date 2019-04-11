title: Sequence of Numbers
--- |
  We can generate a sequence of numbers using `range()` function. Example:
---
type: live-code
id: 434b4dee-32f4-4a0a-a8ad-4c5f4a6f53a7
code: |
  for number in range(0, 10):
    print(number)
--- |
  Think of it like this: `range(n1, n2)` function generates a sequence of numbers from `n1` to `n2 - 1`. And you can iterate through this sequence as you would iterate through any list. It has many applications as we'll see later.

  A variation of `range()` function is `range(n2)`. In this case, you would get a sequence of numbers from `0` to `n2 - 1`. Basically, `n1` is assumed to be `0`. Example:
---
type: live-code
id: 4894042a-c0d4-4d26-bab0-6b3d1afeef19
code: |
  for number in range(10):
    print(number)

---
type: testless-coding-question
id: 6f183850-af45-4a70-bdd4-62ac9b13dbf8
question: |
  Print numbers 10 to 20 (20 included) using `range()` function.
code: |
  # your code goes here

---
type: testless-coding-question
id: 1256dcf8-8c2a-4d19-bdea-70ac9f020939
question: |
  Print numbers 0 to 7 (7 included) using `range()` function.
code: |
  # your code goes here

---
type: multiple-choice-question
id: f7bac3d8-4184-44a3-a597-461d545d6f84
question: |
  `range(8)` would give you a sequence of numbers from 0 to 7. True or False?
options:
  - text: "true"
    correct: true
  - text: "false"

---
type: testless-coding-question
id: 3d33dd45-2ab8-4cb7-929e-cff190b62278
question: |
  Generate 10 random numbers between 1 and 1000. Use the `range()` function to repeat the random number generation. Use the `random.randint()` function to generate random number.
code: |
  import random

  # your code goes here
---
type: testless-coding-question
id: 5b8899de-30ca-4029-a868-1a530f86a0f7
question: |
  Ask the user for 5 numbers. Print the largest number. Use `range()` function to repeatedly ask for a number.
code: |
  # your code goes here

---
type: testless-coding-question
id: f5d80d89-83f4-458e-a354-a2ed64b049e5
question: |
  Ask the user for two numbers (let's call them `n1` and `n2`). Print all numbers between `n1` and `n2` (where these two numbers are excluded). Use the `range()` function.
code: |
  # your code goes here
