title: List Operations
--- |
  Here is a quick tour of various list methods that we would use in these exercises.

---
type: live-code
id: ed1449fc-fc39-4956-bb31-6c199998dfec
code: |
  one_to_ten = [1, 2, 3, 4, 5, 6, 7, 8]

  # how to complete this list? By 'appending' 9 and 10 to this list.
  one_to_ten.append(9)
  one_to_ten.append(10)

  one_to_ten

---
type: live-code
id: b1a40442-a223-4a8f-b29a-15cf94d29a1b
code: |
  prime_numbers = [1, 2, 3, 5, 7, 11]
  more_prime_numbers = [13, 17, 19]

  # can we "extend" the prime_numbers to include remaining primes?
  prime_numbers.extend(more_prime_numbers)
  prime_numbers

---
type: live-code
id: 7cb2044b-bea1-44b8-99ff-809a44b1c357
code: |
  one_to_ten = [1, 2, 4, 5, 6, 7, 9, 10]

  # number 3 is missing from the list. can we "insert" it?
  # first argument is index number and second argument is
  # the value to be inserted.
  one_to_ten.insert(2, 3)
  one_to_ten

  # number 8 is also missing. can you insert it at the correct index?

---
type: live-code
id: 74781ef5-d8b1-4478-9fe2-4c9b3f0cd668
code: |
  one_to_ten = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12]

  # this has extra numbers. can we "remove" them?
  one_to_ten.remove(11)
  one_to_ten.remove(12)

  one_to_ten

---
type: live-code
id: c2feada2-5f5f-4ecb-b52a-edda98385aa0
code: |
  one_to_ten = [1, 2, 3, 9, 4, 5, 6, 7, 8, 9, 10]

  # number 9 has shown up twice? can we "pop" it from index #3?
  one_to_ten.pop(3)
  one_to_ten

---
type: live-code
id: 66de33b5-79b8-411b-9ff1-689d5ecd1be4
code: |
  random_numbers = [4, 6, 6, 4, 5, 6, 6, 3, 5, 3, 4, 4, 3, 5, 6, 3, 4, 6, 3, 5]

  # can we find out the "count" of number 5 in this list?
  random_numbers.count(5)

---
type: live-code
id: c6269932-1bbd-4056-a5c0-2a7cbee9a03e
code: |
  fruits = ['apple', 'orange', 'pineapple', 'kiwi', 'mango']

  # what's the "index" of pineapple?
  print('pinepple index:', fruits.index('pineapple'))

  # if you give it a fruit that's not on list, what happens?
  print('grape index:', fruits.index('grape'))
  
---
type: testless-coding-question
id: d7b839b9-6796-4159-b448-8b2db7b56c41
question: |
  Using `append()` and `remove()` methods, transform the `grocery_items` to remove apple and add pineapple.
code: |
  grocery_items = ['apple', 'orange', 'cabbage', 'okra', 'milk', 'eggs']

  # your code goes here.

---
type: testless-coding-question
id: 21b28f6f-5c87-41b8-96d4-632a3221f530
question: |
  Using `extend()` method, extend the `grocery_items` to include all items from `optional_grocery_items`.
code: |
  grocery_items = ['apple', 'orange', 'cabbage', 'okra', 'milk', 'eggs']
  optional_grocery_items = ['biscuits', 'samosas']

  # your code goes here.

---
type: testless-coding-question
id: 1a03437c-95d8-4ef9-9e9d-b505804ad6a1
question: |
  Someone forgot to include number `7` in the following list. Using the `insert()` method, please add `7` to its rightful place.
code: |
  one_to_ten = [1, 2, 3, 4, 5, 6, 8, 9, 10]

  # your code goes here

---
type: testless-coding-question
id: ffcc5fe3-f044-40b5-8bb8-35b903e6422f
question: |
  I tossed a coin 21 times and recorded the result (heads or tails) in a list. Using the `count()` method, can you tell me whether I got heads more or the tails?
code: |
  coin_toss = ['H', 'H', 'T', 'H', 'T', 'T', 'H', 'T', 'T', 'T', 'H', 'H', 'T', 'H', 'H', 'H', 'H', 'H', 'H', 'T', 'H']

  # your code goes here

---
type: testless-coding-question
id: 4290738d-729d-4899-870c-8633158812e3
question: |
  Keep asking the user to enter a number till the user enters `0`. Append all these numbers to a list. When the user enters `0`, print the list (just use `print(list_name)`).
code: |
  # your code goes here

---
type: testless-coding-question
id: 114c01c7-0842-43d0-abf7-a426f9292463
question: |
  You are given a list in the following code. By using a series of `insert()`, `pop()` and `append()` methods, transform the list so that it has numbers 1-10 in correct order.
code: |
  one_to_ten = [9, 8, 1, 2, 3, 4, 6]

  # your code goes here
