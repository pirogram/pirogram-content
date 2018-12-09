title: List Indexing
--- |
  All the items in a list are placed in a specific order. This strict ordering makes it easy for us to number them in sequence. For example, here is a list of websites that I have opened in my browser tabs:

  ```Python
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io'
  ]
  ```

  One way to think about this list is that these are the five websites open in my browser right now. Another way to think about it is the sequence in which these websites are open in the browser. For example, 1st tab has `'www.gmail.com'`, 2nd tab has `'www.pirogram.com'`, last tab has `'atom.io'` etc.

  Here is an example that shows how you can retrieve the item at position 2 from the list. The general syntax is `list_name[position_number]`. So, to get website at position 2 from our list, we could use `websites[2]`.

---
type: live-code
id: daa92d0a-1724-48d2-b92d-2f6e8edf4a0f
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io'
  ]

  websites[2]
--- |
  If you run this example, you may find the result unexpected. You would have thought that position 2 will give you `'www.pirogram.com'`. However, position 2 gives you `'www.twitter.com'`. Why did that happen? That's because the position numbers in a list start from `0` and not `1`. Following illustration will help you understand the same:

  ![list indexing](assets/img/list-indexing.svg)

  Why do the list position numbers start from `0` instead of `1`. It's a perspective thing. Early programming languages made this choice and it has become the default since then. You'll get used to it (after a while).

  Another nuance here is the terminology. Instead of _position_, people use the term _index_. There isn't much philosophy behind it. While it's more convenient to think in terms of position, _index_ is the term adopted by programming languages.

  ## Indexing in Reverse Direction
  Another indexing scheme (aka the position numbering scheme) is to start from the last item and count backwards. Here is an illustration for the same:

  ![list reverse indexing](assets/img/list-reverse-indexing.svg)

  Now, why do we start with `-1` instead of `0` when counting backwards? Well, `0` is already taken. Isn't it? Of course, it would seem much more consistent to start counting from `1` while counting forward but that ship sailed several decades ago.

  Try changing the index number in the following example and see how it works.

---
type: live-code
id: 34b730c0-73a7-4e18-b3c1-241961240fed
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io'
  ]

  websites[-2]

--- |

  ## List Index Out Of Range

  If you run the following code, you would get an error:

---
type: live-code
id: 34b730c0-73a7-4e18-b3c1-241961240fed
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io'
  ]

  websites[7]

--- |
  Since you have only 5 items in the list, the valid index range is 0 to 4 (or -5 to 4 to be precise). Index 7 is out of the range of valid index numbers.

  ## What the index!

  We can also find out the index at which a given item is present. This can help us with questions like: which browser tab has `'www.pirogram.com'`.

---
type: live-code
id: cad78902-efa1-4bf7-972d-e60e3e36c2aa
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io'
  ]

  websites.index('www.pirogram.com')

--- |
  What happens when the value you are looking for is not present in the list? Try changing the website name in the above code and find out.

  ## Updating List

  Let's say, we opened `'www.goodreads.com'` in the tab at index 3. That means, our list must be changed to reflect that. How do we do that?

---
type: live-code
id: eee25369-9755-4032-a3e1-f1d691db605f
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io'
  ]

  websites[3] = 'www.goodreads.com'
  websites
--- |
  We can also use reverse indexing to update the list:

---
type: live-code
id: 85e6a39e-0a7b-4afe-9cf7-d98ca2632c01
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io'
  ]

  websites[-2] = 'www.goodreads.com'
  websites

--- |
  Just by combining the operations so far, we can solve more interesting problems. For example, we could say that open `'www.goodreads.com'` in the tab that currently has `'www.twitter.com'`. How do we do that?

---
type: live-code
id: 85e6a39e-0a7b-4afe-9cf7-d98ca2632c01
code: |
  websites = [
    'www.gmail.com',
    'www.pirogram.com',
    'www.twitter.com',
    'hckrnews.com',
    'atom.io'
  ]

  twitter_index = websites.index('www.twitter.com')
  websites[twitter_index] = 'www.goodreads.com'
  websites

---
type: categorization-question
id: 9f73ec0f-f252-42e8-889c-e9c4eb4ee827
question: |
  Select the correct answers from dropdown based on following list definition:

  ```python
  grocery_items = ['apple', 'orange', 'cabbage', 'okra', 'milk', 'eggs']
  ```
categories: ['apple', 'orange', 'cabbage', 'okra', 'milk', 'eggs']
mappings:
  "grocery_items[0]": apple
  "grocery_items[2]": cabbage
  "grocery_items[-1]": eggs
  "grocery_items[-5]": orange

---
type: categorization-question
id: 5c916d1b-70c2-4566-84bb-0662d13e5b5a
question: |  
  Select the correct answers from dropdown based on following list definition:

  ```python
  one_to_ten = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
  ```
categories: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 'Invalid']
mappings:
  "one_to_ten[4]": 5
  "one_to_ten[7]": 8
  "one_to_ten[10]": Invalid
  "one_to_ten[-3]": 8
  "one_to_ten[-10]": 1

---
type: categorization-question
id: c82a3b38-819b-4cba-a852-d5faa46c3edb
question: |  
  Select the correct answers from dropdown based on following code:

  ```python
  numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
  numbers[3] = 11
  numbers[-5] = 12
  ```
categories: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]
mappings:
  "one_to_ten[3]": 11
  "one_to_ten[7]": 8
  "one_to_ten[5]": 12
  "one_to_ten[-3]": 8
  "one_to_ten[-7]": 11

---
type: categorization-question
id: 185f75b3-2ed7-4fec-a527-b99776ff14d0
question: |
  Select the correct answers from dropdown based on following list definition:

  ```python
  potterverse = ['Snape', 'Dumbledore', 'Harry', 'Hermione', 'Ron', 'He-Who-Cannot-Be-Named']
  ```
categories: [0, 1, 2, 3, 4, 5]
mappings:
  "What's the list index for Harry?": 2
  "What's the list index for Ron?": 4

---
type: categorization-question
id: 361ffb79-35fc-4680-b389-116a11d83dbd
question: |
  Select the correct answers from dropdown based on following code:

  ```python
  potterverse = ['Snape', 'Dumbledore', 'Harry', 'Hermione', 'Ron', 'He-Who-Cannot-Be-Named']

  potterverse[2] = 'Neville'
  potterverse[-2] = 'Sirius'
  ```
categories: [0, 1, 2, 3, 4, 5, 'Not In List']
mappings:
  "What's the list index for Harry?": "Not In List"
  "What's the list index for Ron?": "Not In List"
  "What's the list index for Sirius?": 4

---
type: categorization-question
id: b90bce07-fab1-4346-a0e3-9a75bd0cbbe9
question: |
  Select the correct answers from dropdown based on following list definition:

  ```python
  flowers = ['rose', 'lotus', 'lily', 'dahlia', 'daisy']
  ```
categories: [-1, -2, -3, -4, -5]
mappings:
  rose: -5
  dahlia: -2

---
type: testless-coding-question
id: b981a2ad-6819-4826-86a5-29ee1ebeb9a3
question: |
  Correct the `print` statement in the following code so that it prints `Harry Won Over He-Who-Cannot-Be-Named`.
code: |
  potterverse = ['Snape', 'Dumbledore', 'Harry', 'Hermione', 'Ron', 'He-Who-Cannot-Be-Named']

  print(potterverse[0], 'Won Over', potterverse[4])

---
type: testless-coding-question
id: 4d450c2c-75e0-46d5-bbf6-9176334e3e4b
question: |
  In the following code, add flower `petunia` to the list in such a way that the code prints 'I love petunia' instead of 'I love lily'. Note, you must not modify the `print` statement. Just modify the list definition.
code: |
  flowers = ['rose', 'lotus', 'lily', 'dahlia', 'daisy']

  print('I love', flowers[2])
