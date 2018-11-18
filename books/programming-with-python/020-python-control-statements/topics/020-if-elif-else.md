title: If, Elif, Else
--- |
  Example of `if/else`: ask the user to enter his/her name. Greet the user if the name was entered. But if the user entered blank, greet the world.
---
type: live-code
id: b6ab0bb9-1685-40ca-a50f-ab77b99d28c3
code: |
  name = input("What's your name? ")
  if name != '':
    print('Hello', name)
  else:
    print('Hello World')

--- |
  Here is another example that uses `if/elif/else`: ask the user to enter a number. If the number is less than 10, print `single digit`. If the number is bigger than 99, print `triple digit`. Otherwise, print `double digit`.

---
type: live-code
id: c412d334-f1d8-4344-a64b-889011ff6bfe
code: |
  num = input("Enter a number: ")
  num = int(num)

  if num < 10:
    print('single digit')
  elif num < 100:
    print('double digit')
  else:
    print('triple digit')

---
type: testless-coding-question
id: 562d199a-2364-40d6-90f1-7f0db7ee93bb
question: |
  Ask the user to enter a number. If the number is greater than or equal to `0`, print `it's a +ve number`. Otherwise, print `it's a -ve number.`
code: |
  # your code goes here.

---
type: testless-coding-question
id: ae96c340-2b6c-4b6c-a32e-d9bf25417296
question: |
  Ask the user to enter a number. If the number is even, print `even number`. Otherwise, print `odd number`. Hint: if a number `num` is even, `num%2` would be `0`.
code: |
  # your code goes here.

---
type: testless-coding-question
id: af7f6fc1-583d-4708-94e2-0aa003733d0a
question: |
  Ask the user to enter two numbers. Print the number that is greater. If both numbers are equal, print `better luck next time`. An example session would look like the following

  ```
  Enter a number: 2
  Enter another number: 4
  4 is bigger than 2.
  ```

  Another example:
  ```
  Enter a number: 3
  Enter another number: 3
  better luck next time
  ```

code: |
  # your code goes here.

---
type: testless-coding-question
id: fd839e16-e39f-4941-b18f-acbbbd79d466
question: |
  Ask the user to enter a number. If this is an even number, print it as it is. If it is an odd number, print the even number next in sequence. For example, if the user enters `4`, print `4`. If the user enters `7`, print `8`.

  Hint: a number is odd if `number % 2` yields `1`.
code: |
  # your code goes here.
