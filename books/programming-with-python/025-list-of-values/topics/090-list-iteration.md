title: List Iteration
--- |
  The most frequently performed operation on a list is going over the list one value at a time and doing something with that value. Some of the problems where this would be useful are:
  * if you have a list of numbers and you want to calculate the sum total of the same, you would go through all the numbers and add them up.
  * if you have a list of emails and you want to find out which ones were sent on a specific date, you would again go through all emails and check for the date range.

  The process of going through list items one by one is called _list iteration_. Before we look at the idiomatic way of doing it in Python, we'll do it using the `while` loop. Just to build upon our existing knowledge.
---
type: live-code
id: dfc88818-4f51-4d94-b408-521e5aeb2a4f
code: |
  numbers = [9, 2, 34, 2, 7, 8, 23, 4, 9]

  index = 0
  while index < len(numbers):
    print( numbers[index] )
    index += 1
--- |

  We basically created a variable called `index` which starts at value `0`. We get into a `while` loop that terminates when the `index` has reached the end of the list. We increment the `index` within the loop by `1`.

  A more concise way to iterate over the elements of a list is to use the `for item in list:` syntax. Here is the solution to same problem but this one uses `for` loop.

---
type: live-code
id: 6456b9f4-02c0-4651-849e-d1af23847d1d
code: |
  numbers = [9, 2, 34, 2, 7, 8, 23, 4, 9]

  for num in numbers:
    print(num)

--- |
  It's doing exactly what we did with the `while` loop. The only difference is that in this particular case, Python would internally maintain the index rather than we maintaining it in our code.

  We'll now do some exercises to get you comfortable with list iteration.

---
type: testless-coding-question
id: 53187c7f-d119-4b4f-a338-34fbc039b213
question: |
  You are given a list of numbers. Count the number of +ve values.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  # your code goes here

---
type: testless-coding-question
id: 41c989d8-ca66-4008-b8f3-515fb815c474
question: |
  You are given a list of numbers. Count the number of -ve values.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
         2,  -2,  17, -20,  -5,  14, -16]

  # your code goes here

---
type: testless-coding-question
id: 78c975c1-6255-4260-832f-5909ef2de224
question: |
  You are given a list of numbers. Find the sum total of these numbers.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
      2,  -2,  17, -20,  -5,  14, -16]

---
type: testless-coding-question
id: 426aa07d-9b5b-423b-ae6e-8b45cad0778d
question: |
  You are given a list of numbers. Find the product of all the numbers. For example, for the list `[1, 2, 3]`, the product would be `1 * 2 * 3` (i.e. `6`).
code: |
  numbers = [2, 3, 9, 3]

---
type: testless-coding-question
id: 80ca21ac-73de-472f-bc1d-1ff298b76234
question: |
  You are given a list of numbers. Find the product of +ve numbers (greater thhan `0`) in the list.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
      2,  -2,  17, -20,  -5,  14, -16]

---
type: testless-coding-question
id: bd147490-ac93-4004-8f24-daa59c2b82a1
question: |
  Your a given a list of numbers. Create two new lists called `pos_numbers` and `neg_numbers`. Store all +ve numbers in the `pos_numbers` list and all -ve numbers in the `neg_numbers` list.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
        2,  -2,  17, -20,  -5,  14, -16]

---
type: testless-coding-question
id: 6a962ba9-908f-46e1-bd01-625f438b3a90
question: |
  You are given a list of numbers. Find the largest number from the list.
code: |
  numbers = [7,   0, -18,   0,  16, -18,   8,  -4,  10, -18,  -9,  -9,  -2,
        2,  -2,  17, -20,  -5,  14, -16]

---
type: testless-coding-question
id: 07fd3ad2-ff83-4e80-8064-05b69447980a
question: |
  You are given a list of lists of numbers. Find the sum of all the numbers across all lists.

  Hint: you can run nested `for` loop as follows:
  ```Python
  for number_list in numbers:
    for number in number_list:
      ...
  ```
code: |
  numbers = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
  ]
---
type: testless-coding-question
id: 05dd0f10-413c-47bc-8338-db1f942e4ca3
question: |
  You are given a list of lists of numbers. Find out the number of lists that have a `0` in it. In the given list of lists, there are 2 lists with `0`.
code: |
  numbers = [
    [1, 2, 3],
    [3, 0, 1],
    [9, 1, 0]
  ]
