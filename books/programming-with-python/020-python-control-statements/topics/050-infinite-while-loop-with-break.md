title: Infinite While Loop With Break
--- |
  We'll keep asking the user to enter a number till the user enters `0`. We'll then print the total number of times the user entered a number.
---
type: live-code
id: 2a8b606f-2485-4ecd-8d81-837812c3fb7e
code: |
  count = 0
  while True:
    num = input("Please enter a number: ")
    num = int(num)
    if num == 0:
      break
    else:
      count = count + 1

  print("You entered", count, "numbers")

---
type: testless-coding-question
id: 5dd899ba-9b7d-44ac-ade8-701b5e867955
question: |
  The objective of this program is to get user to enter an even number. Keep asking the user to enter an even number as long as the user enters only odd number. When the user enters an even number, print `good job`. Example:

  ```
  Even number please: 3
  Even number please: 5
  Even number please: 4
  Good Job!
  ```
code: |
  # your code goes here.

---
type: testless-coding-question
id: 90f0e9fd-2652-40c1-a445-06e366800f4e
question: |
  Keep asking the user to enter a number as long as the user enters an even number. As soon as the user enters an odd number, print the total number of times an even number was entered. For example:

  ```
  A number please: 4
  A number please: 2
  A number please: 3
  You entered 2 even numbers.
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: 09065d6a-4c4f-4d03-a679-888130b39881
question: |
  Keep asking the user to enter a number till the user enters `0`. Print the sum of all the numbers that user entered. For example:

  ```
  A number please: 4
  A number please: 2
  A number please: 3
  A number please: 0
  Sum of numbers you entered: 9
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: 95dd5cd7-44f9-488d-b746-f778e27b0667
question: |
  Keep asking the user to enter a number till the user enters `0`. Print the average of all the numbers that the user entered. For example:

  ```
  A number please: 4
  A number please: 2
  A number please: 3
  A number please: 0
  Average of numbers you entered: 3
  ```

  Hint: To calculate average, you should keep track of sum and count of numbers that user entered.
code: |
  # your code goes here

---
type: testless-coding-question
id: a8d2eadd-3096-491c-94e4-75dcfe789583
question: |
  Keep asking the user to enter a number till the user enters `0`. Print the largest number entered by the user. If the user entered `0` as the first number, print `what what? what what?`.
code: |
  # your code goes here

---
type: testless-coding-question
id: 38c2ccef-95d0-4d33-85b3-9eba786969c3
question: |
  Generate a random number between 1 & 20 and ask the user to guess it. If the guess is smaller than the random number, print `go higher`. If the guess is bigger than the random number, print `go lower`. Keep doing this till the user makes correct guess. If the guess is correct, print `Good Job!`.

  The following code can be used to generate random number between 1 and 20:

  ```
  import random
  random_number = random.randint(1, 20)
  ```
code: |
  import random
  random_number = random.randint(1, 20)

  # your code goes here

---
type: testless-coding-question
id: 56debad4-307c-44f2-a112-1bfcdba6bdf0
question: |
  Generate a random number between 1 & 20 and print it. Keep doing this till you get a random number that's divisible by 5.
code: |
  # your code goes here
