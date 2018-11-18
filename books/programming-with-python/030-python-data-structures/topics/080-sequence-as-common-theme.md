title: Sequence As Common Theme
--- |
  As you probably noticed, there are a lot of similarities among Python's built-in data structures (`list`, `tuple`, `set`, `dict`). The underlying theme is that of a _sequence_. In this section, we'll develop a way of thinking about these data structures as variations of a _sequence_. And in the following sections, we'll further develop that way of thinking.

  First, let's look at all the data structures that we worked with so far:

---
type: live-code
id: 6749e42c-216d-45d9-a955-a5ca6389d1e5
code: |
  fruits_list = ['apple', 'orange', 'banana', 'pineapple']
  fruits_tuple = 'apple', 'orange', 'banana', 'pineapple'
  fruits_set = {'apple', 'orange', 'banana', 'pineapple'}
  fruits_dict = {'apple': 4, 'orange': 3, 'banana': 3, 'pineapple': 1}

  print('list:', fruits_list)
  print('tuple:', fruits_tuple)
  print('set:', fruits_set)
  print('dict:', fruits_dict)

--- |
  ## Length

  They all support the `len()` function to get the number of items in the _sequence_.

---
type: live-code
id: 245025cd-98b7-4fd3-81bf-c71a9f4f6c4c
code: |
  print('list:', len(fruits_list))
  print('tuple:', len(fruits_tuple))
  print('set:', len(fruits_set))
  print('dict:', len(fruits_dict))

--- |
  ## Indexing

  `list`, `tuple` and `dict` have a notion of _index_. `set` does not have a notion of index. Also, index for `list` and `tuple` is a sequential number but for `dict`, index can be any data type.

---
type: live-code
id: 21e06ab9-df73-4730-9a45-0b71049f2613
code: |
  # for list and tuple, index is a sequential number.
  print('fruits_list[0]:', fruits_list[0])
  print('fruits_tuple[2]:', fruits_tuple[2])

  # for dict, index is whatever we set it to be.
  print('fruits_dict["orange"]', fruits_dict["orange"])

--- |
  ## Ordering

  `list` and `tuple` also have a notion of _order_. All items within these two data structures are ordered by their index number. On the other hand, `set` and `dict` do not have a notion of order. You cannot say _"give me 4th item from this `set` or that `dict`"_ but you can say that for a `list` or a `tuple`.

---
type: live-code
id: 49e9ec00-b004-4e62-ab94-177e10f870de
code: |
  # get 3rd item from the sequence.
  print('fruits_list[2]:', fruits_list[2])
  print('fruits_tuple[2]:', fruits_tuple[2])

  # nothing like this for set or dict. there is no notion of 3rd item.

--- |
  ## Mutability

  `list`, `set` and `dict` are mutable. Once created, you can still put things in and take things out. Not so with `tuple`. A `tuple` once created cannot be modified in any way.

  So, how do you add/remove things for various data structures?

---
type: live-code
id: 84e9fe66-74a4-4c26-ae36-aa9d43fa3fd8
code: |
  fruits_list = ['apple', 'orange', 'banana', 'pineapple']

  # In a list, you always add new items by specifying its position
  # (aka index) within the list.
  fruits_list.insert(1, 'kiwi')

  # Even when you use "append", you are effectively specifying the
  # position (aka index) as -1.
  fruits_list.insert(-1, 'guava')
  fruits_list.append('cherry')

  # For removing items from list, you can either provide the index or item details.
  fruits_list.pop(-2) # remove the 2nd last item which is 'guava'
  fruits_list.pop()   # remove the last item (which is 'cherry')

  fruits_list.remove('kiwi') # remove first instance of 'kiwi'

  fruits_list
---
type: live-code
id: 0c228937-993c-4f59-b1b3-b90d1f3a5bd4
code: |
  fruits_set = {'apple', 'orange', 'banana', 'pineapple'}

  # In a set, there is no concept of index. So, you just add or discard.
  fruits_set.add('guava')

  fruits_set.discard('apple')

  fruits_set
---
type: live-code
id: 4d7e8013-ada6-4b6b-8045-b729d450a6ed
code: |
  fruits_dict = {'apple': 4, 'orange': 3, 'banana': 3, 'pineapple': 1}

  # In a dict, you always add or remove by index.

  fruits_dict['kiwi'] = 6

  del fruits_dict['pineapple']

  fruits_dict

---
type: multiple-choice-question
id: fb12ad1c-2e16-4dc3-b5b5-d0c15624bfca
question: |
  Which of the following data structures are indexed?
options:
  - text: list
    correct: true
  - text: tuple
    correct: true
  - text: set
  - text: dict
    correct: true

---
type: multiple-choice-question
id: 164c3efa-f869-4a0c-8b27-f20ea696d456
question: |
  Which of the following data structures are mutable?
options:
  - text: list
    correct: true
  - text: tuple
  - text: set
    correct: true
  - text: dict
    correct: true

---
type: multiple-choice-question
id: 0d6d8892-a0c2-40a1-8e5c-e2659bcb6a81
question: |
  Which of the following data structures are ordered?
options:
  - text: list
    correct: true
  - text: tuple
    correct: true
  - text: set
  - text: dict
