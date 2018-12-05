title: List Iteration
--- |
  The most frequently performed operation on a list is going over the list one value at a time and doing something with that value. Some of the problems where this would be useful are:
  * if you have a list of numbers and you want to calculate the sum total of the same, you would go through all the numbers and add them up.
  * if you have a list of emails and you want to find out which ones were sent on a specific date, you would again go through all emails and check for the date range.

  The process of going through list items one by one is called _list iteration_. Before we look at the idiomatic way of doing it in Python, we'll do it using the `while` loop. Just to build upon our existing knowledge. Here is the code that can find the sum total of all numbers in a list:
---
type: live-code
id: 71b0b81e-ab89-4f77-9afe-816e0645d5e9
code: |
  numbers = [9, 2, 34, 2, 7, 8, 23, 4, 9]

  index = 0
  total = 0
  while index < len(numbers):
    total += numbers[index]
    index += 1

  print('Total:', total)
--- |

  We basically created a variable called `index` which starts at value `0`. We get into a `while` loop that terminates when the `index` has reached the end of the list. We increment the `index` within the loop by `1`. And of course, because wanted to calculate the total of the numbers, we have another variable `total` which starts at `0` but we keep adding the individual numbers to that total.

  A more concise way to iterate over the elements of a list is to use the `for item in list:` syntax. Here is the solution to same problem but this one uses `for` loop.

---
type: live-code
id: eef14f6d-1c1f-4eb9-b034-72d3e4d1a1f3
code: |
  numbers = [9, 2, 34, 2, 7, 8, 23, 4, 9]

  total = 0
  for num in numbers:
    total += num

  print('Total:', total)

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
