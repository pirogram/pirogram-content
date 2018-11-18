title: sorted()
--- |
  `sorted()` function takes an `iterable` and returns a list of sorted items. Note: it takes an `iterable` and not just a `list` as input. Anything that you can give to `for` is an iterable (e.g. `for item in iterable:`).

---
type: live-code
id: 9b9dc383-891f-4f3e-bf3a-8ea001993fd7
code: |
  sorted([4, 2, 39, 9, 1])

--- |
  String is also an `iterable`. The output is still a `list`.

---
type: live-code
id: 4d90d7a0-6207-409d-a341-df4be2d207e0
code: |
  # sorted list of vowels
  sorted('ouaie')

--- |
  `dict` is also an `iterable`. When you iterate over a `dict`, you effectively iterate over the keys of the `dict` (remember `for key in dict:`). Passing a dict to `sorted()` will give you dictionary keys in a sorted list.

---
type: live-code
id: 3687575d-bf5e-4351-b43b-90149dc90ddf
code: |
  fruit_basket = {'apple': 4, 'peach': 9, 'banana': 2, 'pineapple': 3, 'kiwi': 6}

  sorted(fruit_basket)

--- |
  Here are two ways to print your fruit basket. One prints it in seemingly random order and the other one prints it in a sorted order.

---
type: live-code
id: 424b0465-9a07-4f8f-b012-fb00644c34fd
code: |
  fruit_basket = {'apple': 4, 'peach': 9, 'banana': 2, 'pineapple': 3, 'kiwi': 6}

  for fruit_name in fruit_basket:
    print(fruit_name, '->', fruit_basket[fruit_name])

---
type: live-code
id: 5d9fcdbd-ff7f-4150-ba25-eccd1f922b75
code: |
  fruit_basket = {'apple': 4, 'peach': 9, 'banana': 2, 'pineapple': 3, 'kiwi': 6}

  # print it in sorted fashion.
  for fruit_name in sorted(fruit_basket):
    print(fruit_name, '->', fruit_basket[fruit_name])

---
type: testless-coding-question
id: 1a746260-82ab-4887-a7af-fd072cbf2421
question: |
  Keep asking the user to enter a number till user enters `0`. Print the numbers in increasing order.
code: |
  # your code goes here

---
type: testless-coding-question
id: 000b6ef4-b0ac-46da-a990-3bcad4c96686
question: |
  Ask the user to enter multiple words separated by space (` `) character. Print the words sorted in alphabetical order.

  Hint: you should use `split()` to extract words from the string entered by user.
code: |
  # your code goes here

---
type: testless-coding-question
id: 99f77096-be96-403b-9a73-18a4a078dafd
question: |
  Ask the user to enter multiple numbers separated by space (` `) character. Print unique numbers entered by the user and the count of each number in increasing order. For example, if the user entered `4 2 4 3 9 2 2`, the program would print:
  ```
  2 -> 3
  3 -> 1
  4 -> 2
  9 -> 1
  ```

  Hint: Split the string by ` `. Use `dict` for this problem. Each number entered by user is a key and the value is number of times that number was entered.
code: |
  # your code goes here

---
type: testless-coding-question
id: 8d990e15-399e-476a-a006-910b78f2141d
question: |
  Ask the user to enter multiple words separated by space (` `) character. Print unique words entered by the user and the number of times that word was mentioned. Print it in alphabetical order of the words. For example, if user entered: `brown fox crazy dog sleepy fox jumpy dog`, the program would print:

  ```
  brown -> 1
  crazy -> 1
  dog -> 2
  fox -> 2
  jumpy -> 1
  sleepy -> 1
  ```
code: |
  # your code goes here
