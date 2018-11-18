title: Stripping
--- |
  Stripping denotes remove certain types of characters from the beginning or end of the string. It's very useful when cleaning up data.

---
type: live-code
id: 449fa23e-35f3-45d1-bf15-f802e57c1846
code: |
  # remove leading and trailing whitespace
  '     spacious    '.strip()

---
type: live-code
id: bdd86a48-1967-470d-8ab1-1d249de16846
code: |
  # remove only leading whitespace
  '     spacious    '.lstrip()

---
type: live-code
id: c5ef213e-fe67-481e-92dc-0718cdaf00b8
code: |
  # remove only trailing whitespace
  '     spacious    '.rstrip()

---
type: live-code
id: 37037251-4cc7-45b7-914f-d284865a0288
code: |
  # remove multiple characters
  'weirdo?!!'.strip('!?')

---
type: testless-coding-question
id: 5bc9c783-9174-4abb-acf4-b04db1379fa5
question: |
  Ask the user to enter comma separated list of numbers. Print the sum of those numbers. Note: the user can enter numbers as `1, 2, 3` or `1,2,3` or `1,2, 3 ,4` etc.
code: |
  # your code goes here

---
type: testless-coding-question
id: 6a8b98a3-ee54-42c0-9aae-da657bb926bf
question: |
  Ask the user to enter a comma separated list of words. Form a sentence with those words. Note, the user can enter words as `hello, world`, `hello,world` or `hello ,world` etc.
code: |
  # your code goes here
