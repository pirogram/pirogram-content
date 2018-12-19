title: While With Branching
--- |
  You can put `if-else` based branching logic inside a loop. For example, the following code prints even numbers between 1 to 20:
---
type: live-code
id: 3fd87b31-3e5e-4817-978d-d15daa5c598d
code: |
  number = 1

  while number <= 20:
    if number%2 == 0:
      print(number)

    number += 1
---
type: testless-coding-question
id: a580dcc3-4a6a-4281-bd28-736de7eb4e61
question: |
  Ask the user to enter a number. Print all _odd_ numbers from 1 to the number entered by the user.
code: |
  # your code goes here

---
type: testless-coding-question
id: 7ce306ce-0d52-45e4-88e2-5779f17d4882
question: |
  Ask the user to enter a number. Find the sum of all _even_ numbers from 1 to the number entered by user. For example, if the user entered `4`, the program would print `6` (i.e. 2 + 4).
code: |
  # your code goes here
---
type: testless-coding-question
id: 3993c313-ca5f-4547-9679-6ab8af2a4816
question: |
  Print the first 10 _even_ numbers in the fibonacci series.
code: |
  # your code goes here

---
type: testless-coding-question
id: a1ec3d7e-4021-4bba-9e80-0dc774302e42
question: |
  Ask the user to enter a number. Print the count of digits in that number. For example, if the user enters `342`, the program would print `3` since it has three digits.

  Hint: Take the number and keep dividing it by 10 till you are left with 0. For example, `342 // 10` gives you `34`; `34 // 10` gives you `3`; `3 // 10` gives you `0`.
code: |
  # your code goes here
