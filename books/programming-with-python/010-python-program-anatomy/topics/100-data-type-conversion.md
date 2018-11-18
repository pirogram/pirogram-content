title: Data Type Conversion
--- |
  Let's say, we want to write a small program. It would ask the user to enter two numbers and it would print the sum of those numbers. So, if the user entered numbers `4` and `2`, the program would print `The sum of 4 and 2 is 6.` Let's see how we can approach it.

---
type: live-code
id: 786bfbed-52f3-4d55-9079-d02e38eb4dea
code: |
  number1 = input("Please enter a number: ")
  number2 = input("Please enter another number: ")

  print('The sum of', number1, 'and', number2, 'is', number1 + number2, '.')

--- |
  If you enter `4` and `2`, the program would print `42` instead of `6`. What's the problem? Well, if you remember, the `input()` function yields the value of type `str`. So, it yields strings `'4'` and `'2'` respectively instead of integers `4` and `2`. This is where type conversion comes into the picture. You can convert the string `'4'` to integer `4` by using the function `int('4')`.

  Here is a corrected program:

---
type: live-code
id: 6b824f37-666a-4328-b6ab-bfbfccab793a
code: |
  number1 = input("Please enter a number: ")
  number1 = int(number1)

  number2 = input("Please enter another number: ")
  number2 = int(number2)

  print('The sum of', number1, 'and', number2, 'is', number1 + number2, '.')

---
type: testless-coding-question
id: 98637e5f-a028-449b-8cb3-45c2ae83ef69
question: |
  Write a program that asks the user to enter two number. Print the multiplication of two numbers. For example, if the user entered `4` and `2`, print `The multiplication of 4 and 2 is 8.`
code: |
  # your code goes here

---
type: testless-coding-question
id: afaf20c5-4ccb-46c8-8979-db58074bfbc6
question: |
  Write a program that asks the user to enter two number. Subtract the second number from first number and print the result. For example, if the user entered `4` and `2`, print `4 - 2 is 2.`
code: |
  # your code goes here
