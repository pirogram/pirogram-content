title: While Loop With Flag
--- |
  There is a special class of problems for which there is a special technique you can apply. As usual, we'll first familiarize ourselves with the problem and then learn the technique.

  We want to keep asking the user to enter a number till the user enters `0`. When the program finishes, we would print whether the user entered an even number or not. Here is one way to approach it:
---
type: live-code
id: 42af4c6b-d49b-4c8f-b200-237176f41d9d
code: |
  even_count = 0

  while True:
    num = int( input('A number please: '))
    if num == 0:
      break

    if num%2 == 0:
      even_count += 1

  if even_count:
    print('You entered an even number.')
  else:
    print('You did not enter an even number.')

--- |
  You can think of this as if you are going on an investigation and at the end of the investigation, you print the result. There are many problems that fall in this category and we would work with some of them now.

---
type: testless-coding-question
id: 6d563db6-1993-4be4-83d0-34744a4bc177
question: |
  Ask the user to enter a number. If the number is prime, print, `prime number` else print `not a prime number`.
code: |
  # your code goes here

---
type: testless-coding-question
id: 0e1c3834-f9dc-4f3d-b351-1734568f9011
question: |
  Generate 10 random numbers between 1 and 100 (using `random.randint(1, 100)`). If you got a number greater than `90`, print `got a big number` else print `didn't get a big number`.
code: |
  # your code goes here
