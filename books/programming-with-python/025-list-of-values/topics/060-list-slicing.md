title: List Slicing
--- |

  There are times when you would have a very long list. For example, think of all your emails. When you organize them in a list, it would run very long. It would be impractical to display all your emails on one page. That's why, the email clients show you 50 emails at a time and then you can step through previous 50 or next 50 emails.

  In the world of lists, this concept is referred to as slicing. You have a long list (of emails) and you are taking a slice of 50 emails at a time to show to the users.

  Slicing is a very useful concept and it shows up in solving many problems. Another example would be to think of a book as a list of letters. Each chapter of the book is a slice of the complete list. Each page is yet another slice from the list of letters of a chapter. A paragraph is yet another slice and so is a sentence. Every word can also be thought of as a slice.

  Extracting a slice from the list looks very similar to extracting an item by position. Let's go back to the list of outcomes from tossing a coin 8 times:

  ```python
  toss_outcomes = ['H', 'H', 'T', 'H', 'T', 'T', 'T', 'H']
  ```

  If you want to know the outcome of 4th coin toss, you would use `toss_outcomes[3]`. If you want to create a slice of outcomes 4th to 7th, you would use `toss_outcomes[3:7]`. `[3:7]` means start at index `3` and stop right before index `7` (i.e. index `6`). Again, it can take some time to get comfortable with this and there are plenty of examples in this topic to develop familiarity.

  The following code snippets show some of the functionality related list slicing. Play around with it by changing various numbers in the slice and see how things change. Also try to use some invalid index numbers in the slice.

  What happens when you use `[:]` as slice? What happens when you put same number on either side of `:` e.g. `[4:4]`? What happens when you put two consecutive numbers e.g. `[4:5]`? Finally, what happens when you put bigger number first e.g. `[5:3]`?

---
type: live-code
id: ad8d5f2f-b764-4b29-8238-8393a14cef5e
code: |
  zero_to_nine = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

  # simple slicing
  zero_to_nine[1:4]

---
type: live-code
id: 780d46ca-1134-466c-ace9-8f66aed869ad
code: |
  zero_to_nine = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

  # slicing with -ve index numbers
  zero_to_nine[-6: -2]
---
type: live-code
id: 7ad0b25d-bc88-4a2c-8766-8ac364d7ffe2
code: |
  zero_to_nine = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

  # slice that starts from 0th index (or beginning of the list)
  zero_to_nine[:3]

---
type: live-code
id: 6014d497-0aa5-4a53-a2dd-ad15b2b18952
code: |
  zero_to_nine = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

  # slice that runs all the way to end (i.e. last index)
  zero_to_nine[4:]

---
type: multiple-choice-question
id: 6e4feb1e-aeb3-4b5f-8fe5-2070af478629
question: |
  For the following list:

  ```python
  grocery_items = ['apple', 'orange', 'cabbage', 'okra', 'milk', 'eggs']
  ```

  What's the value of `grocery_items[1:3]`?
options:
  - text: |
      `['apple', 'orange', 'cabbage', 'okra']`
  - text: |
      `['orange', 'cabbage', 'okra', 'milk']`
  - text: |
      `['orange', 'cabbage', 'okra']`
  - text: |
      `['orange', 'cabbage']`
    correct: true

---
type: multiple-choice-question
id: 59e46bbe-9bf1-41ee-bc28-0403826f3798
question: |
  For the following list:

  ```python
  one_to_ten = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
  ```

  What's the value of `one_to_ten[4:9]`?
options:
  - text: |
      `[4, 5, 6, 7, 8, 9]`
  - text: |
      `[5, 6, 7, 8, 9, 10]`
  - text: |
      `[4, 5, 6, 7, 8]`
  - text: |
      `[5, 6, 7, 8, 9]`
    correct: true

---
type: testless-coding-question
id: d12b6345-3b5f-4eaf-ab31-a60ecc925f4b
question: |
  Change the slicing in the following code so that it prints `[3, 4, 5]`.
code: |
  one_to_ten = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

  print(one_to_ten[2:9])

---
type: testless-coding-question
id: db8cfa5b-ce30-4d23-b6bf-b3ddc7ce72f5
question: |
  Change the slicing in the following code so that it prints `[6, 7, 8, 9]`. Continue to use the -ve index numbers.
code: |
  one_to_ten = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

  print(one_to_ten[-8:-1])

---
type: testless-coding-question
id: e6ae0275-55c4-412a-88ca-517abf2e879a
question: |
  Create a slice of `potterverse` that has only good characters (i.e. Dumbledore to Ron) and print it. Do it with +ve index numbers as well as -ve index numbers.
code: |
  potterverse = ['Snape', 'Dumbledore', 'Harry', 'Hermione', 'Ron', 'He-Who-Cannot-Be-Named']

---
type: multiple-choice-question
id: 63378ef6-af3e-43db-b423-79225eb07fac
question: |
  Given the following list, choose the options that would result in a slice of `[1, 2, 3, 4]`:

code: |
  one_to_ten = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

options:
  - text: |
      `one_to_ten[:4]`
    correct: true
  - text: |
      `one_to_ten[0:4]`
    correct: true
  - text: |
      `one_to_ten[:3]`
  - text: |
      `one_to_ten[0:3]`
  - text: |
      `one_to_ten[:5]`
  - text: |
      `one_to_ten[0:5]`

---
type: multiple-choice-question
id: 6e695d55-c9d4-4a96-bd41-f71bcb01b919
question: |
  Given the following list, choose the options that would result in a slice of `[8, 9, 10]`:

code: |
  one_to_ten = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

options:
  - text: |
      `one_to_ten[7:10]`
    correct: true
  - text: |
      `one_to_ten[7:]`
    correct: true
  - text: |
      `one_to_ten[-3:]`
      correct: True
  - text: |
      `one_to_ten[6:9]`
  - text: |
      `one_to_ten[8:10]`
  - text: |
      `one_to_ten[8:]`