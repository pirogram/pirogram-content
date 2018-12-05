title: Dict Problems
--- |
  This is a simple program to accept numbers from the user and track how many times a number has been entered in a dictionary. When the user enters 0, the program prints the dictionary.
---
type: live-code
id: 3f87b28b-42af-4945-a31b-4fceca204772
code: |
  numbers = dict()
  while True:
      # get a number from user.
      num = input("A number please: ")
      num = int(num)

      # break if the number is 0
      if num == 0:
        break

      # get the current count for this number. set count to 0 if number is not in dictionary.
      if num in numbers:
        numbers[num] = numbers[num] + 1
      else:
        numbers[num] = 1

  print(numbers)
---
type: testless-coding-question
id: 5f9199b5-f2b5-40c9-ac56-ca99df3d6e8e
question: |
  Keep asking the user to enter a word till the user enters blank (i.e. `''`). Store all these words in a dictionary such that the key is the word and value is the number of times that word was entered. Print the dictionary.

  Example session:

  ```
  A word please: Hi
  A word please: Hello
  A word please: Hi
  A word please:
  You Entered: {'Hi': 2, 'Hello': 1}
  ```
code: |
  # your code goes here
