title: Splitting
--- |
  Splitting a string is among the most common things you'll do with strings. Let's look at the method and patterns for using this method.

---
type: live-code
id: be184b67-defb-40bb-9c40-24061634737a
code: |
  s = 'this string has many words'
  words = s.split()
  words

---
type: live-code
id: 420d70ec-de30-45f1-a98b-9a05589ef072
code: |
  # you can also split using any other character.
  s = 'apple,banana,peach,orange'
  fruits = s.split(',')
  fruits

---
type: live-code
id: 11524bde-e3dc-454d-a79e-f2554b1c710d
code: |
  # you can split using another string as well.
  s = 'apple, banana, peach, orange'
  fruits = s.split(', ')
  fruits

--- |
  Let's look at the power of splitting applied to different problems..

---
type: live-code
id: 909ce3ed-983f-4ac0-ab60-c6fc03bdf0f0
code: |
  s = 'A lazy dog was sleeping. A quick fox was jumping. And the sun was shining.'

  # How to find out the number of sentences in this string?
  # By splitting on '. '
  sentences = s.split('. ')
  print('Sentences ->', sentences)

  print('No of sentences ->', len(sentences))

---
type: testless-coding-question
id: 84bf5eb9-2003-4022-b08a-5efa04d1e397
question: |
  Given a multiline string, print the number of words in each line. For example, the output for the string in code section should be:
  ```
  line 1 - 2 words
  line 2 - 3 words
  line 3 - 2 words
  ```

  Note: you can split the string on `\n` to separate out the lines.
code: |
  s = '''old pond
  frog leaps in
  water's sound'''

  # your code goes here

---
type: testless-coding-question
id: d529b6ea-7533-468f-81ae-22fd265d4e96
question: |
  Given a string, find out the count of number based words. For example, the string `'1984 was hotter than 1985'` has two number based words (1984 & 1985). You can use `.isdecimal()` method.
code: |
  s = 'Year 1984 was hotter than 1985 which itself was hotter than 1986'

  # your code goes here

---
type: testless-coding-question
id: 6915180f-0dd6-48b4-aabd-d0d8e4537a79
question: |
  Given a multiline string, find out the count of 4 letter words.
code: |
  s = '''Voices I heard
  One after another
  Voices that merged into each other
  Voices that overlapped each other'''

---
type: testless-coding-question
id: 35ea7d4f-4800-4f1b-9e4e-99ebb099e52e
question: |
  Given a multiline string, find out the count of **distinct** 4 letter words.
code: |
  s = '''Voices I heard
  One after another
  Voices that merged into each other
  Voices that overlapped each other'''

---
type: testless-coding-question
id: 48fb7977-f845-463f-8bb2-745dcd9e2eea
question: |
  Ask the user to enter a comma separated list of numbers. Print the sum of those numbers. For example, if the user enters `1, 2, 3, 4`, the program prints `10`.
code: |
  # your code goes here
