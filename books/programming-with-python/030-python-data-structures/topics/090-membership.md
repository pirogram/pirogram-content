title: Membership
--- |
  All Python data structures that we studied so far (`list`, `tuple`, `set` and `dict`) provide a uniform way of checking whether a given element is present or not. Examples:

---
type: live-code
id: 2244200b-9642-48fd-9e63-3891534ab2ed
code: |
  fruits_list = ['apple', 'orange', 'banana', 'pineapple']

  if 'apple' in fruits_list:
    print("apple is in fruits_list")
  else:
    print("apple is not in fruits_list")

---
type: live-code
id: 30243509-fbaf-4a95-9941-e232bffb7431
code: |
  fruits_list = ['apple', 'orange', 'banana', 'pineapple']

  if 'brinjal' in fruits_list:
    print("brinjal is in fruits_list")
  else:
    print("brinjal is not in fruits_list")
---
type: live-code
id: 30aee11a-c032-4f8b-8e45-84959c96e29d
code: |
  fruits_tuple = 'apple', 'orange', 'banana', 'pineapple'

  'apple' in fruits_tuple
---
type: live-code
id: 2b14c2d1-d050-4a9e-8a55-56b7a0081c2e
code: |
  fruits_set = {'apple', 'orange', 'banana', 'pineapple'}

  'apple' in fruits_set

---
type: live-code
id: e8ab6307-32da-4fcb-8919-5f3b2aeae7ac
code: |
  fruits_dict = {'apple': 4, 'orange': 3, 'banana': 3, 'pineapple': 1}

  'apple' in fruits_dict

---
type: testless-coding-question
id: 320b8b7a-5fe7-44af-a453-25b221e13671
question: |
  Generate 10 unique random numbers between 1 and 20. Print the unique random numbers as well as the number of attempts it took to get 10 unique numbers in 1 to 20 range. Use `set` to store numbers and membership check in your code.

  Sample output from the program:

  ```
  Hold tight. Generating 10 random numbers between 1 and 20...
  Set of 10 unique random numbers: {2, 4, 9, 3, 13, 11, 7, 19, 17, 1}
  Number of attempts to generate 10 unique random numbers: 21
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: 213347a6-047c-4e67-9388-bd9f3ce51839
question: |
  Generate 10 unique random numbers between 1 and 20. Now, ask the user to enter a number. If the number is among the generated random numbers, print `It's one of the random numbers`. Otherwise, print `It's not one of the random numbers`. Keep asking the user till the user enters 0.
code: |
  # your code goes here.

---
type: testless-coding-question
id: b2efe0e6-43be-4389-b931-fa257b1f652d
question: |
  Your are given a list of school's basketball team players. Write the program for a user to give you a name and the program would print whether that name is in the basketball team or not. Keep asking the user till user enters blank.
code: |
  player_names = ["Althea", "Linnea", "Tabitha", "Mckinley", "Leopoldo", "Lucio", "Bert", "Taylor", "Geri", "Dulce", "Johnny", "Kyung", "Fredia", "Karol", "Lelia", "Rolland", "Linwood", "Spencer", "Bernadette", "Alayn"]

  # your code goes here.
