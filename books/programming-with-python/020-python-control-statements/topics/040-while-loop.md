title: While Loop
--- |
  Think of this as count-up problem. We'll ask the user to enter a number which is less than 20. We'll then print all numbers from 0 to the number that user entered.
---
type: live-code
id: 6593a6b2-852c-430c-a516-d7f63054c878
code: |
  upper_number = input("Please enter a number: ")
  upper_number = int(upper_number)

  num = 0
  while num <= upper_number:
    print(num)
    num = num + 1

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
id: a7ce894d-434b-4818-9bcb-a2f8ee47d298
question: |
  Ask the user to enter two numbers. Print all numbers in between. The user could enter the smaller number followed by a bigger one or vice versa. For example:

  ```
  Enter a number: 4
  Enter another number: 7
  Numbers in between are:
  5
  6
  ```

  Also

  ```
  Enter a number: 7
  Enter another number: 4
  Numbers in between are:
  5
  6
  ```
code: |
  # your code goes here.

---
type: testless-coding-question
id: ea53a3a9-009b-44a7-a6ef-69fbff00b903
question: |
  Think of this one as count up or count down problem. Ask the user to enter two numbers. If the user enters smaller number first, count up to the bigger number. If the user enters bigger number first, count down to the smaller number. Examples:

  ```
  Enter a number: 4
  Enter another number: 7
  Numbers in between are:
  5
  6
  ```

  ```
  Enter a number: 7
  Enter another number: 4
  Numbers in between are:
  6
  5
  ```

  If there is no number in between the two numbers (e.g. in case the user enters `4` and `4` or `4` and `5`), print `Better luck next time`.
code: |
  # your code goes here.

---
type: testless-coding-question
id: 638f9609-b80d-48dd-bb3d-5cd400bae83e
question: |
  Ask the user to enter two numbers. Print all even numbers that fall between these two numbers. For example, if the user enters `4` and `9` (or `9` and `4`), the program prints `6` and `8`.
code: |
  # your code goes here

---
type: testless-coding-question
id: f15d8ba9-d324-4505-aa2f-d925aca4aad7
question: |
  Ask the user to enter a number. Print whether that number is a prime number or not. For example:

  ```
  Enter a number: 7
  7 is a prime number!
  ```

  ```
  Enter a number: 8
  8 is divisible by 2. Not a prime!
  ```
code: |
  # your code goes here
