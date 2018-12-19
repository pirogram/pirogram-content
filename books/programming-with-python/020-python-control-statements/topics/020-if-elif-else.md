title: if, elif, else
--- |
  _If you are hungry, eat food. Else, go out and play._

  In our day to day life, we make many decisions. When you think about the anatomy of a decision, usually, there is a condition and there is an action dependent on the condition to be true or false. For example, "being hungry" is a _condition_, "eating food" is an _action_ dependent on the _condition_ of "being hungry".

  Bulk of programming also boils down to taking _actions_ based on _conditions_. Consider the following example. We ask the user to enter a number. If the number is greater than 0 (_condition_), we print that it is a +ve number (_action_).

---
type: live-code
id: 5e00f4a5-cf03-4cd2-a9fa-92ba0461bb1b
code: |
  number = int(input('Enter a number: '))

  if number > 0:
    print(number, 'is a +ve number')

--- |
  If you enter a number greater than 0, the _condition_ `number > 0` would be met and the corresponding _action_ would be taken.

  The generic syntax for conditional execution is:
  ```Python
  if some_condition_is_true:
      execute_this_statement
      and_this_statement
  ```

  You write `if` followed by a condition followed by `:`. Whatever statements you want to execute when condition is true, indent them to the right so that visually, they look as if they are under the `if` statement.

  Let's look at another example:
---
type: live-code
id: 3acb97bc-0c49-4e01-8796-1f5562881782
code: |
  number = int(input('Enter a number: '))

  if number > 0:
    print(number, 'is a +ve number')

  print('Bye')
--- |
  In this example, `print(number, 'is a +ve number')` would be executed only when the condition `number > 0` is true. However, `print('Bye')` would be executed regardless.

  We can also specify some statements to be executed when the condition is not true. For example:
---
type: live-code
id: 3acb97bc-0c49-4e01-8796-1f5562881782
code: |
  number = int(input('Enter a number: '))

  if number > 0:
    print(number, 'is a +ve number')
  else:
    print(number, 'is not a +ve number')

  print('Bye')
--- |
  We can handle more conditions within the same flow:
---
type: live-code
id: d9704d9b-997c-44c1-b358-770a43baf15a
code: |
  number = int(input('Enter a number: '))

  if number > 0:
    print(number, 'is a +ve number')
  elif number < 0:
    print(number, 'is a -ve number')
  else:
    print(number, 'is zero')

  print('Bye')

--- |
  We can also nest the `if-else` blocks:

---
type: live-code
id: 365d3eed-ee43-4b10-80f7-dfb1492a0f2b
code: |
  number = int(input('Enter a number: '))

  if number > 0:
    if number%2 == 0:
      print(number, 'is a +ve even number')
    else:
      print(number, 'is a +ve odd number')
  elif number < 0:
    if number%2 == 0:
      print(number, 'is a -ve even number')
    else:
      print(number, 'is a -ve odd number')
  else:
    print(number, 'is zero')

  print('Bye')

--- |
  This could also be written as:
---
type: live-code
id: b1cb1c3c-6172-49d3-92da-d876816a4225
code: |
  number = int(input('Enter a number: '))

  if number > 0 and number%2 == 0:
    print(number, 'is a +ve even number')
  elif number > 0 and number%2 == 1:
    print(number, 'is a +ve odd number')
  elif number < 0 and number%2 == 0:
    print(number, 'is a -ve even number')
  elif number < 0 and number%2 == 1:
    print(number, 'is a -ve odd number')
  else:
    print(number, 'is zero')

  print('Bye')

---
type: testless-coding-question
id: ba0b09af-5dd3-438f-acc9-c7e7a8991d7e
question: |
  Ask the user to enter his/her name. If the user enters blank, print `Hello World`, otherwise, print `Hello <name>`. Example sessions:
  ```
  What's your name: Ravi
  Hello Ravi
  ```
  ```
  What's your name:
  Hello World
  ```
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
id: 9b1cae11-8679-40eb-b3b3-ddd77341dcb3
question: |
  Ask the user to enter two numbers. Print the number that's bigger. Example session:
  ```
  Enter a number: 4
  Enter another number: 7
  7 is the bigger number.
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: 4a5458a4-7c11-4917-a538-e5c137fb1578
question: |
  Ask the user to enter two numbers. Print which number is bigger and which is smaller. Example session:
  ```
  Enter a number: 4
  Enter another number: 7
  7 is the bigger number.
  4 is the smaller number.
  ```

code: |
  # your code goes here

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

---
type: testless-coding-question
id: 2bb58028-77b9-4815-96cf-329f34075232
question: |
  Ask the user to enter three numbers. Print the number that is biggest. Example:
  ```
  Enter a number: 4
  Enter another number: 7
  Enter yet another number: 5
  7 is the biggest number.
  ```
code: |
  # your code goes here
---
type: testless-coding-question
id: 8a313079-2ff5-46de-b267-6760c4f1d1ba
question: |
  Ask the user to enter a number. If the number is divisible by `3`, print `Fizz`. If the number is divisible by `5`, print `Buzz`. If the number is divisible by both `3` and `5`, print `FizzBuzz`. Otherwise, just print the number.
code: |
  # your code goes here.

---
type: testless-coding-question
id: aecd87e2-33cd-4665-bd5e-08507fb9a995
question: |
  Ask the user to enter two numbers. If both the numbers are +ve, print `+ve`. If both are -ve, print `-ve`. If one is +ve and another is -ve, print `+ve and -ve`.
code: |
  # your code goes here.

---
type: testless-coding-question
id: 876fd3e6-8e7e-4058-92a3-2dc87f342b40
question: |
  Ask the user to enter 3 numbers. If one of these numbers is the average of the other two, print `yay`. Otherwise, print `nay`.
code: |
  # your code goes here.

---
type: testless-coding-question
id: 139a384b-65ab-4690-a114-0437c15c55ff
question: |
  Ask the user to enter two numbers. If both are even, print `even`. If both are odd, print `odd`. If one is even and one is odd, print `even and odd`.
code: |
  # your code goes here.
