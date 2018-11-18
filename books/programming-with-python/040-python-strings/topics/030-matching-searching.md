title: Matching/Searching
--- |
  What kind of letters are there in the string and do they follow some pattern?

---
type: live-code
id: 7f3455f9-1feb-4ce7-987d-76e05895f060
code: |
  # is it all lower case?

  print('lower ->', 'lower'.islower())
  print('Upper ->', 'Upper'.islower())

---
type: live-code
id: 321cb7a3-8319-477f-b8f5-ef00f7d96e9d
code: |
  # is it all upper case?

  print('lower ->', 'lower'.isupper())
  print('Upper ->', 'Upper'.isupper())
  print('UPPER ->', 'UPPER'.isupper())

---
type: live-code
id: 639a6e94-e905-43ff-9c7c-05930f01e722
code: |
  # is it all decimal numbers?

  print('123 ->', '123'.isdecimal())
  print('abc ->', 'abc'.isdecimal())
  print('abc123 ->', 'abc123'.isdecimal())

---
type: live-code
id: 3ed16782-06bb-4f9a-b1c0-0e442e9359c9
code: |
  # is it all alphabets (i.e. A-Z or a-z)?

  print('ABC ->', 'ABC'.isalpha())
  print('abc ->', 'abc'.isalpha())
  print('123 ->', '123'.isalpha())

---
type: live-code
id: fbcddc6f-1da5-4ee9-9c6f-4fe6fc3718f4
code: |
  # does it end with something specific?

  s = 'www.google.com'
  s.endswith('com')

---
type: live-code
id: c1e51448-3b20-493e-b185-662b63b22a7c
code: |
  s = 'www.wikipedia.net'
  s.endswith('com')

---
type: live-code
id: 65c0d8be-d339-4afc-9f74-dee60866bfdb
code: |
  # does it start with something specific?
  s = 'www.google.com'
  s.startswith('www')

---
type: live-code
id: 93424ec8-6629-4e74-8805-f6ecf449982b
code: |
  s = 'http://www.google.com'
  s.startswith('www')

---
type: live-code
id: 712f146b-6078-47fb-9eb0-8cb6abd7f5dd
code: |
  # What's the index of a specific substring in the string.
  s = 'www.google.com'
  s.find('.')

---
type: live-code
id: a8ce8593-538c-48f2-972d-10ead06d72d2
code: |
  # if the substring doesn't exist in the string, we get -1.
  s = 'www.google.com'
  s.find('http')

--- |
  You can also find() within an index range of string.

---
type: live-code
id: 14e38000-6cf0-420d-9c8d-64feec62c207
code: |
  'www.google.com'.find('.', 0, -1)
---
type: live-code
id: 49df82f8-82de-4143-8c3c-61b0ce6868b3
code: |
  'www.google.com'.find('.', 4, -1)

---
type: live-code
id: 1a5cdd62-21b2-4c5b-8414-57b799a5639f
code: |
  'www.google.com'.find('.', 12, -1)

---
type: fill-in-the-blank-question
id: 46d3f58a-a6d6-40f8-abda-3714f15e9a78
question: |
  Given the following string, what's the output from various code fragments?

  ```Python
  s = 'http://www.pirogram.com'
  ```
blanks:
  - label: s.find( 'pi' )
    answer: 11
  - label: s.find( '.' )
    answer: 10
  - label: s.find( 'pi', -10, -1 )
    answer: -1
  - label: s.find( '.', -10, -1 )
    answer: 19

---
type: multiple-choice-question
id: b948a055-85eb-4e34-b655-f8ed9f613075
question: |
  What does `'Pirogram'.isupper()` give you?
options:
  - text: "False"
    correct: True
  - text: "True"
  - text: "1"
  - text: "0"
  - text: None

---
type: testless-coding-question
id: 7afeb646-21d1-48b4-8844-1c31c1b9b28a
question: |
  Keep asking the user to enter a word till the user enters blank `''`. Print the count of words that start or end with letter `'i'`.
code: |
  # your code goes here

---
type: testless-coding-question
id: e60f5cfa-dc21-425f-893e-e83a2fb6ea56
question: |
  Keep asking the user to enter a word till the user enters blank `''`. Print the count of words that are hyphenated (have a `'-'` character).
code: |
  # your code goes here
