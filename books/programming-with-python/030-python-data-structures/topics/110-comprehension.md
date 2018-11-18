title: Comprehension
--- |
  The purpose is to create a new list, tuple, set or dict by transforming the elements of an existing list, tuple, set or dict.

  Let's say, we have a list of numbers. We want to create another list out of it wherein each number has been halved. Using iteration, we could do it as follows:
---
type: live-code
id: fc0ee1a0-c5f5-414f-b157-8153d0aea5fa
code: |
  numbers = [1, 2, 3, 4]

  halved_numbers = []  
  for number in numbers:
    halved_numbers.append(number/2)

  halved_numbers
--- |
  Comprehension provides a more compact syntax for achieving the same.
---
type: live-code
id: c970772c-2e1f-47ac-a749-58dc33790471
code: |
  numbers = [1, 2, 3, 4]

  halved_numbers = [number/2 for number in numbers]

  halved_numbers
--- |
  Let's build upon this. Suppose, we have a few temperature readings that were measured in Fahrenheit. We want to convert them in Celsius. Here is how you can do it for a list.

---
type: live-code
id: ca523b82-159d-4934-80f5-3a134d90cf36
code: |
  # list comprehension example

  temperatures_in_f = [105, 110, 97, 88]

  temperatures_in_c = [(item - 32) * 5/9 for item in temperatures_in_f]
  temperatures_in_c

--- |
  `dict` also supports comprehension syntax. Here is an example:

---
type: live-code
id: d5c66f88-d155-4f86-afc3-16786451366f
code: |
  # dict comprehension example

  temperatures_in_f = {'SFO': 105, 'LA': 110, 'Seattle': 97, 'Vancouver': 88}

  temperatures_in_c = {city_name:(temp_f - 32) * 5/9 for city_name, temp_f in temperatures_in_f.items()}

  temperatures_in_c

--- |
  For `dict`, another interesting example is the following where we create a `dict` out of a `list`. The key is the number in the list and the value is square root of that number.
---
type: live-code
id: d0f93faa-0436-4e4c-bb4c-69195d164f74
code: |
  import math

  numbers = [1, 4, 9, 16]

  sqrt_numbers = {n: math.sqrt(n) for n in numbers}
  sqrt_numbers
  
---
type: testless-coding-question
id: 78a1bc64-52d9-4ce7-93a3-b1667d21c0be
question: |
  Given a list of temperature readings in Celsius, create a corresponding list of temperature readings in Fahrenheit (`f = c * 9/5 + 32`). Use list comprehension.
code: |
  temperatures_in_c = [37, 26, 42, 33, 39]

  # your code goes here.

---
type: testless-coding-question
id: 992f565e-84b0-4c0b-825c-29d189677a3a
question: |
  Given a list of numbers, create a list of squares of those numbers. For example, given `[1, 2, 3]`, create a list `[1, 4, 9]`. Use list comprehension.
code: |
  numbers = [2, 4, 7, 3]

  # your code goes here

---
type: testless-coding-question
id: af65895f-4aae-449d-b40f-0ad7026638c9
question: |
  Given a list of words, create a new list where each word is in lower case. For example, given `['What', 'is', 'your', 'NAME']`, create a list `['what', 'is', 'your', 'name']`. You can use `.lower()` method on strings (`'What'.lower()` will give you `'what'`). Use list comprehension.
code: |
  words = ['These', 'words', 'should', 'BE', 'Made', 'ALL', 'LowerCase']

  # your code goes here

---
type: testless-coding-question
id: ac12b47a-ac37-4bc4-a721-6c1c216e45f2
question: |
  Given a dictionary of temperature readings in Celsius, create a corresponding dict of temperature readings in Fahrenheit (`f = c * 9/5 + 32`). Use dict comprehension.
code: |
  temperatures_in_c = {'SFO': 37, 'Vancouver': 26, 'New Delhi': 42,
    'Seattle': 33, 'LA': 39}

  # your code goes here

---
type: testless-coding-question
id: b04b12bd-106a-48ee-955f-05a7974166b4
question: |
  Given a list of numbers, create a dictionary where key is the number from the list and value is square of that number. For example, given the list `[1, 2, 3]`, the dictionary would be `{1: 1, 2: 4, 3: 9}`. Use dict comprehension.
code: |
  numbers = [2, 4, 7, 3]

  # your code goes here

---
type: testless-coding-question
id: 1cb68af9-356d-43d9-a75a-3b9f31a47e2a
question: |
  Given a list of words, create a dictionary such that the key is the word from the list and value is the same word in lower case. Use dict  comprehension. For example, `['Two', 'Words']` should give `{'Two': 'two', 'Words': 'words'}`.
code: |
  words = ['These', 'words', 'should', 'BE', 'Made', 'ALL', 'LowerCase']

  # your code goes here
