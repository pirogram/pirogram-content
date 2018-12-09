title: List Slicing
--- |
  Have you ever carved out a slice from an apple (or pineapple)? One way to think about creating a slice of apple is that out of a big apple, you created a smaller apple. It's just a way of thinking. But it's a useful way of thinking in current context because we can extend it to _list slicing_.

  So, what's list slicing? Once again, let's look at the list of websites that are open in my browser. I can pick a slice of this list from index 1 to index 4.

---
type: live-code
id: 67e068c6-c11e-46df-910c-71c0a8d3fe8a
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io',
    'www.goodreads.com',
    'www.python.org'
  ]

  websites[1:5]
--- |
  The syntax of picking up a slice of a list is very similar to that of picking an individual item. The only difference is that instead of giving 1 index number within `[]`, we give it an _index range_. The index range `[1:5]` should be interpreted as:
  * Start at index `1` (and _include_ the item at that index)
  * Go upto index `5` (and _exclude_ the item at that index)

  That's why, the slice we just created doesn't have `'www.goodreads.com'` since that's on index `5`. We go upto that index but do not include the item at that index.

  A list slice is a fully functional list. In fact, once you have created a list slice, there is no way for you to tell whether it's a slice taken from another list or it's a list created from scratch.

  First, we'll look at a couple of variations of list slicing. After that, we'll also look at how we can use the slicing mechanism in updating a list.

  ## Slicing Variations

  One variation is to skip the second index number in the slicing range. For example, we can use `[1:]` as the index range. This is interpreted as go till end of the list. Example:

---
type: live-code
id: d49e4022-1969-48b1-9d9a-6915cac5429d
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io',
    'www.goodreads.com',
    'www.python.org'
  ]

  websites[1:]
--- |

  In the aforementioned example, the slice includes all items from index `1` onwards.

  Yet another variation is to skip the first index number (e.g. `[:5]`). This means start from index `0`. Example:
---
type: live-code
id: f021382c-37b7-4495-a57f-96f886e9bf80
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io',
    'www.goodreads.com',
    'www.python.org'
  ]

  websites[:5]
--- |
  In this example, the slice includes all items starting from index `0` and going all the way upto `5` (_excluding_ item at index 5).

  What happens if we skip the first and second index numbers from slice range? We get a full replica of the original list:
---
type: live-code
id: 0ce36b7e-f00c-43ae-9fe9-78ae3bfc84f2
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io',
    'www.goodreads.com',
    'www.python.org'
  ]

  websites[:]
--- |

  And finally, slices can be created using -ve indexing as well. Example:
---
type: live-code
id: e886c6b3-8cb8-48bb-baf0-59c576e2a7a8
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io',
    'www.goodreads.com',
    'www.python.org'
  ]

  websites[-5:-2]
--- |

  ## Updating Slices

  When you create a list slice, it's not only a fully functional list, it's also completely independent from the original list. Modifying one of these has no effect on the other. Here is an example:

---
type: live-code
id: 4fcfcf02-901a-4c8a-b618-f3c2d6df1a00
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io',
    'www.goodreads.com',
    'www.python.org'
  ]

  slice = websites[1:4]
  print('original slice:', slice)
  print('original list:', websites)

  # Update the slice.
  slice[0] = 'www.mozilla.org'

  print('modified slice:', slice)
  print('original list:', websites)

  # Update the original list
  websites[2] = 'www.google.com'

  print('modified slice:', slice)
  print('modified list:', websites)  

--- |
  As you would notice from the aforementioned example, the slice and list are independent of each other.

  However, consider the following example:
---
type: live-code
id: 4fcfcf02-901a-4c8a-b618-f3c2d6df1a00
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io',
    'www.goodreads.com',
    'www.python.org'
  ]

  websites[1:3] = ['www.google.com', 'www.mozilla.org']

  websites

--- |
  Here, the behavior is different. In this example, we don't create a slice of the list. Rather, assigned certain values to a portion of the list.

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
    correct: true
  - text: |
      `one_to_ten[6:9]`
  - text: |
      `one_to_ten[8:10]`
  - text: |
      `one_to_ten[8:]`
