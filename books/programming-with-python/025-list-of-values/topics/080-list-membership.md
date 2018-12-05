title: List Membership
--- |
  While dealing with lists, it's very common to check if a given item is in the list or not. For example, if you make a list of all the fruits that your friend likes, from time to time, you would want to find out if a given fruit is in that list or not.

  This is where we introduce two more conditional operators: `in` and `not in`. Let's look at a few examples of these operators.

---
type: live-code
id: 2244200b-9642-48fd-9e63-3891534ab2ed
code: |
  favorites = ['apple', 'orange', 'banana', 'pineapple']

  print('apple' in favorites)

---
type: live-code
id: 75e3eb4d-90ad-4992-add1-76f0c314166b
code: |
  favorites = ['apple', 'orange', 'banana', 'pineapple']

  print('mango' not in favorites)

--- |
  Given that `in` and `not in` are conditional operators (i.e. they yield `True` or `False`), you can use them in `if/else` statements.

---
type: live-code
id: 30243509-fbaf-4a95-9941-e232bffb7431
code: |
  favorites = ['apple', 'orange', 'banana', 'pineapple']

  if 'brinjal' in favorites:
    print("brinjal is in favorites")
  else:
    print("brinjal is not in favorites")
---
type: testless-coding-question
id: b2efe0e6-43be-4389-b931-fa257b1f652d
question: |
  Your are given a list of school's basketball team players. Write the program for a user to give you a name and the program would print whether that name is in the basketball team or not. Keep asking the user till user enters blank.
code: |
  player_names = ["Althea", "Linnea", "Tabitha", "Mckinley", "Leopoldo", "Lucio", "Bert", "Taylor", "Geri", "Dulce", "Johnny", "Kyung", "Fredia", "Karol", "Lelia", "Rolland", "Linwood", "Spencer", "Bernadette", "Alayn"]

  # your code goes here.

---
type: testless-coding-question
id: fa2f33d7-d857-48fd-a2d6-bdfe7f698ce8
question: |
  Keep asking the user to enter a number till the user enters `0`. If the user enters a number that had already been entered, print `that's a duplicate.`.
code: |
  # your code goes here
