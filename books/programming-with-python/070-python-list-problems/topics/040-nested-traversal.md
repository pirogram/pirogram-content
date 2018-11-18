title: Nested Traversal
--- |
  Some of the problems can be solved by using nested traversal technique. Here is an example problem. For each element in a given list of numbers, we'll find the next bigger number that's on the right of the element. For example, if the input is `[20, 9, 4, 12, 11, 6, 15]`, the output of our program will be:

  ```
  20 -> None
  9 -> 11
  4 -> 6
  12 -> 15
  11 -> 15
  6 -> 15
  15 -> None
  ```

  Here is the code for this:
---
type: live-code
id: 43bdd8f4-6ab0-4349-b797-4da32947b199
code: |
  s = input("Please enter a space separated list of numbers: ")
  numbers = [int(elem) for elem in s.split()]

  for i in range(len(numbers)):
    curr_number = numbers[i]
    bigger_number = None

    for next_number in numbers[i:]:
      if next_number > curr_number:
        if not bigger_number:
          bigger_number = next_number
        elif next_number < bigger_number:
          bigger_number = next_number

    print(curr_number, '->', bigger_number)

---
type: testless-coding-question
id: 7dc9e21e-7dd0-41e4-a0d7-7848a1b82be0
question: |
  Ask the user to enter a list of numbers. For each number entered by the user, print the next smaller number to the right in the list. If the user entered `20 9 4 7 12`, the output would be:
  ```
  20 -> 12
  9 -> 7
  4 -> None
  7 -> None
  12 -> None
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: e675d778-88d2-45d7-8813-a2116c571a82
question: |
  Ask the user to enter a list of `+ve` and `-ve` numbers. Find and print the _pairs_ of numbers. For example, if the user enters `1 -3 2 3 6 -1`, the program outputs:

  ```
  1, -1
  -3, 3
  ```

  Note: the `+ve` and `-ve` numbers can occur in any order.

  Hint: to simplify your logic, you can use the trick that such a pair would add upto `0`.
code: |
  # your code goes here

---
type: testless-coding-question
id: a1c519ce-2c46-43bc-a648-9254fb2c957b
question: |
  Ask the user to enter a list of numbers. Identify and print the numbers that have duplicates in the list. Do not sort the list for solving this problem. Use the nested for loop approach.
code: |
  # your code goes here
