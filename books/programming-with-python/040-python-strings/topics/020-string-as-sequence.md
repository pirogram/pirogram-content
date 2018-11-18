title: String As Sequence
--- |
  Strings behave like sequences. What does it mean?

  Strings are like ordered list of characters. Hence, they support indexing, slicing and many other operations that are supported by `list`.

---
type: live-code
id: 8e28781c-d7e5-40e2-9a7f-dbdb8071af62
code: |
  s = 'abcdefghijklmnopqrstuvwxyz'
  s[2]  # list like indexing
---
type: live-code
id: 63d9f487-87c8-44fa-acdc-9d5544454d0b
code: |
  s = 'abcdefghijklmnopqrstuvwxyz'
  s[-2] # -ve index numbers

---
type: live-code
id: 7fd28f16-5689-426b-bec7-0eeb5dd59522
code: |
  s = 'abcdefghijklmnopqrstuvwxyz'
  s[4:8]  # slicing

---
type: live-code
id: 3d66d3a5-8880-4e0a-ad9f-38828e7c4cac
code: |
  s = 'abcdefghijklmnopqrstuvwxyz'

  # len() gives you the length of string
  len(s)

---
type: live-code
id: b20e4d30-626e-4c86-9bbd-7beb1bb00c6e
code: |
  s = 'abcdefghijklmnopqrstuvwxyz'
  'e' in s    # membership check: True

---
type: live-code
id: b878d55b-c015-4450-a352-c3db6ffcc91f
code: |
  s = 'abcdefghijklmnopqrstuvwxyz'
  'E' in s    # membership check: False  

---
type: live-code
id: 88b7794c-57eb-4a16-a6da-a16934851cd9
code: |
  s = 'abcde'

  # strings support iteration
  for letter in s:
    print(letter)

---
type: live-code
id: fd56e70c-32ef-4066-a268-1041d46b5ea2
code: |
  s = 'abcde'

  # index based iteration
  for index in range(0, len(s)):
    print(index, '-', s[index])

--- |
  Strings are immutable like `tuple`. Once created, a string cannot be modified. If you want to transform a string, you must create a new string.

---
type: testless-coding-question
id: 6a781fae-ae5f-49bc-b5cc-8f5800877441
question: |
  Given a string, find out the number of unique letters in that string. (Hint: use can use `set()`). For example, `ram sharma` has `6` unique letters (including space).
code: |
  s = 'lord of the rings is a good movie.'

  # your code goes here.

---
type: testless-coding-question
id: 5b53542e-d750-4ed0-b7d9-2d0bf2bf2761
question: |
  Given a string, print the unique letters in that string and the number of times each of those letters occur in the string. (Hint: use `dict()`).
code: |
  s = 'lord of the rings is a good movie.'

  # your code goes here

---
type: testless-coding-question
id: 14307607-d153-447c-ac6e-ab6ecfa266a4
question: |
  Keep asking the user to enter a word till the user enters blank `''`. Print the count of 4 letter words entered by the user.
code: |
  # your code goes here
