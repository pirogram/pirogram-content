title: Dictionary
--- |
  Let's start with a few examples to get a feel of what dictionaries can do.

---
type: live-code
id: cd642fac-967b-454f-99b6-710d1d1d017f
code: |
  # ingredients for apple pie
  ingredients = {
    'all purpose flour': '2.5 cups',
    'salt': '1/4 teaspoon',
    'butter': '14 tablespoons',
    'large egg': '1',
    'lemon juice': '2 tablespoons',
    'apples': '3 lb'
  }

  ingredients
---
type: live-code
id: 60926908-0389-43cb-a061-de5a1a2c551d
code: |
  # how much butter do we need?
  ingredients['butter']

---
type: live-code
id: 991149c2-db8d-42a9-ae83-3ca66cac58e7
code: |
  # let's add sugar requirements
  ingredients['sugar'] = '2/3 cup'

  # what do the ingredients look like now?
  ingredients

---
type: live-code
id: 2e553f6e-66a6-4564-9f7f-38644fe42666
code: |
  # you can also update the value of an existing key.
  ingredients['butter'] = '12 tablespoons'
  ingredients

---
type: live-code
id: fdca2fde-078a-469b-8b5a-a29101c859c6
code: |
  # what all do we need to make the apple pie?
  ingredients.keys()

---
type: live-code
id: f2bd5cda-fac5-4efd-a3d9-211a3ad69642
code: |
  # can we get the dictionary as a list of items?
  ingredients.items()

---
type: live-code
id: 3f87b28b-42af-4945-a31b-4fceca204772
code: |
  # A simple program to accept numbers from the user and track how many times a number has been entered in a dictionary. When the user enters 0, the program prints the dictionary.

  numbers = dict()
  while True:
      # get a number from user.
      num = input("A number please: ")
      num = int(num)

      # break if the number is 0
      if num == 0:
        break

      # get the current count for this number. set count to 0 if number is not in dictionary.
      count = numbers.get(num, 0)

      # increase the count for this number in dictionary.
      numbers[num] = count + 1

  print(numbers)

---
type: testless-coding-question
id: aa3d61d7-73ee-4854-9ebf-b1aaad6d7594
question: |
  Following information is about an email that I received from Superman. Convert this information into a dictionary.

  ```
  From: Superman
  To: Manas Garg
  Subject: Hi There!
  Date: Day 44 of Galactic Year 1203
  Message: It's high time I start learning programming. How do I get going?
  ```
code: |
  # your code goes here

---
type: categorization-question
id: ed9f68a7-8256-411c-a199-f459f5f8ff94
question: |
  Based on the following code, please select the right answer from dropdown.

  ```python
  closet_items = {
      "shirts": 16,
      "jeans": 5,
      "shorts": 3,
      "t-shirts": 7,
      "socks": 9
  }

  closet_items['ties'] = 2
  closet_items['shorts'] = 4
  ```
mappings:
  "closet_items['shirts']?": 16
  "closet_items['shorts']?": 4
  "closet_items.get('t-shirts')?": 7
  "closet_items['ties']?": 2
  "closet_items.get('shoes')?": This generates an error
  "closet_items.get('shoes', 4)": 4

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
