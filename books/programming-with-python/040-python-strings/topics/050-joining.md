title: Joining
--- |
  Joining multiple strings into one string is also a very common operation and a very useful one.

  One way is to add strings by using `+`.
---
type: live-code
id: 0a0bec2d-b154-4eed-ae30-afb6dd48bd6d
code: |
  name = 'Spiderman'
  salutation = 'Hello'

  greeting = salutation + ' ' + name
  greeting
--- |
  If you have a list of strings that you would like to join, a more efficient way is to use `join` method.

---
type: live-code
id: 43ec844f-4225-458f-aab0-4e2621d3a111
code: |
  words = ['Hello', 'Spiderman!', 'How', 'are', 'you', 'doing?']
  sentence = ' '.join(words)
  sentence

---
type: testless-coding-question
id: d98ffe76-fc8b-45ac-80ae-061ccd6fd4d4
question: |
  Given a list of sentences, join them in a single paragraph.
code: |
  sentences = [
    'old pond', 'frog leaps in', 'water\'s sound'
  ]

  # your code goes here

---
type: testless-coding-question
id: e7f7b48f-9419-4c37-9dd2-f0ce55bfaf20
question: |
  Ask the user to enter a list of comma separated numbers. Convert it into a comma separated string of `even`, `odd`. For example, if the user entered `'1, 2, 3, 4'`, your program should convert it to `'odd, even, odd, even'`.
code: |
  # your code goes here

---
type: testless-coding-question
id: 0843e913-e471-491c-a2a8-2802034f36d5
question: |
  Ask the user to enter comma separated list of numbers. Convert it into a string of comma separated sqaured values of those numbers. For example, if the user entered `'1, 2, 3'`, you should convert it into a string `'1, 4, 9'`.
code: |
  # your code goes here.

---
type: testless-coding-question
id: 2a63f4ee-7ccd-449c-8787-4009af69a557
question: |
  Ask the user to enter a sentence. Print the sentence back after removing unnecessary whitespace characters. For example, if the user enters `There   was a   lazy    dog.`, your program should print `There was a lazy dog.`

  Hint: Split the sentence into a list of words. These words would have multiple blank characters (`''`). Create another list without these characters and join it back.
code: |
  # your code goes here.
