title: While Loop
--- |
  _Keep eating while your stomach is empty_ or _keep ringing the doorbell while the door is still shut_.

  Looping is about repeating an _action_ while a _condition_ is true. For example, the following program keeps asking the user to enter a number unless the user enters an even number.

---
type: live-code
id: 58fb484e-dff8-48aa-b144-0440ea425509
code: |
  import random

  number = int(input('Enter a number: '))

  while number%2 != 0:
    number = int(input('Enter a number: '))

  print('Bye')
--- |
  The syntax for `while` loop is very similar to that of `if`:

  ```Python
  while some_condition_is_true:
    execute_this_statement
    and_this_statement
  ```

  The way you should read this program is:
  ```
  1. if some_condition_is_true
    1.1 execute_this_statement
    1.2 and_this_statement
    1.3 go back to #1
  ```

  Here is another example of looping. In this example, we print numbers 1-10.

---
type: live-code
id: edfaeccb-0b49-4779-9f9f-6ae2e01b0620
code: |
  number = 1

  while number <= 10:
    print(number)
    number += 1

--- |
  This is a very common technique in programming and you'll find a lot of variations of this from time to time. The way you should read this program is:

  Initialize a variable that we would use for condition check.
  ```Python
  number = 1
  ```

  Specify the `while` with appropriate condition.
  ```Python
  while number <= 10:
  ```

  Take the appropriate action:
  ```Python
    print(number)
  ```

  Do something that would eventually make the condition false.
  ```Python
    number += 1
  ```

---
type: testless-coding-question
id: a559c68c-d126-434b-88fe-8d412c3a6de3
question: |
  Think of it like a count-down problem. Ask the user to enter a number. Print a count down of numbers all the way to 0. For example:

  ```
  Enter a number: 6
  Countdown:
  6
  5
  4
  3
  2
  1
  0
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: 3264ca9c-0b0b-4ab8-b1cf-e578d023b0f6
question: |
  Ask the user to enter a number. Print all the _even_ numbers between 0 and the number entered by user.

  Hint: you can initialize a variable as `2` and keep incrementing it by 2 till it's greater than or equal to the number entered by user.
code: |
  # your code goes here

---
type: testless-coding-question
id: a1d47bb3-b74a-4e47-a557-746b595317be
question: |
  Ask the user to enter two numbers. First number is smaller and the second number is bigger. Print all numbers between these two numbers. For example:

  ```
  Enter a number: 4
  Enter another number: 7
  Numbers in between are:
  5
  6
  ```
code: |
  # your code goes here.

---
type: testless-coding-question
id: 7dab2dce-d776-4911-b37e-8408261d5332
question: |
  Ask the user to enter two numbers. First number is bigger and the second number is smaller. Print all numbers between these two numbers. For example:

  ```
  Enter a number: 7
  Enter another number: 4
  Numbers in between are:
  6
  5
  ```
code: |
  # your code goes here.

---
type: testless-coding-question
id: 9eaa8f06-d2bf-40a0-8478-12852ae00544
question: |
  Ask the user to enter a number. Find the sum of all numbers from 1 and the number entered by user. For example, if the user entered `4`, the program would print `10` (i.e. 1 + 2 + 3 + 4).
code: |
  # your code goes here.

---
type: testless-coding-question
id: f3fcc294-07c0-4989-aa8b-78efa763632f
question: |
  Print first 10 numbers in an arithmetic progression that starts with 3 and increases by 4.
code: |
  # your code goes here
---
type: testless-coding-question
id: 91f8cdc6-14a4-4fe7-8847-084d2cfab8cd
question: |
  Print first 15 numbers of the fibonacci series using while loop.
code: |
  # your code goes here
---
type: testless-coding-question
id: 54322b97-bbcb-4ded-aac0-9a6cf257fc14
question: |
  Ask the user to enter a number. Print the multiplication table of that number. For example, if the user enters `9`, the program would print the following:
  ```
  9 x 1 = 9
  9 x 2 = 18
  9 x 3 = 27
  9 x 4 = 36
  9 x 5 = 45
  9 x 6 = 54
  9 x 7 = 63
  9 x 8 = 72
  9 x 9 = 81
  9 x 10 = 90
  ```
code: |
  # your code goes here
