title: What You Can do With Lists
--- |
  Once you have your information structured in a list, you can do many interesting things with it. Let's use some examples.

  Windows Explorer as well as Mac Finder give you the functionality of ordering the file list by file name. It's actually a very trivial thing to do once you have all file names in a list. Here is a demo:
---
type: live-code
id: f9a22d72-8a75-43ec-bdda-fef440b528ed
code: |
  files = ['students.xls', 'expenses.xls', 'lease.doc', 'todo.txt']

  # sort the list entries
  files.sort()

  print(files)
--- |
  That was trivial. Wasn't it? Let's take the example of coin toss. We tossed a coin 8 times and recorded the outcome. We want to find out the number of times we got Heads. We can do with `.count()` method.

---
type: live-code
id: 62e890f4-1c0b-4c39-a91e-63e20391fe5f
code: |
  toss_outcomes = ['H', 'H', 'T', 'H', 'T', 'T', 'T', 'H']

  toss_outcomes.count('H')
--- |
  In fact, we can do many fun things just around this example. For example, we can combine `toss_outcomes.count('H')` which gives us number of heads and `len(toss_outcomes)` that gives us total number of outcomes to get %age of Heads in our tossing game.

---
type: live-code
id: 144975a0-20ea-416c-bd55-2e56cd71dd9e
code: |
  toss_outcomes = ['H', 'H', 'T', 'H', 'T', 'T', 'T', 'H']
  heads_percentage = 100 * ( toss_outcomes.count('H')/len(toss_outcomes) )

  print('%age of heads:', heads_percentage)

--- |
  `.append()` allows you to keep appending new items to the list. It's quite useful when you start out with an empty list of a list with limited values and you receive values in the future. For example, the following code keeps asking the user to enter a number till the user enters 0. Finally, the code prints all the numbers user had entered.

---
type: live-code
id: fc6db8e1-48ac-4c87-be05-7c8c105cbcf5
code: |
  numbers = []

  while True:
    num = int(input('Enter a number (or 0 to stop): '))
    if num == 0: break

    numbers.append(num) # add num to the end of current list.

  print(numbers)

--- |
  `.pop()` removes the last item from the list. An example usage of this method would be print the list items in reverse order.

---
type: live-code
id: e834a8fc-141a-44ff-8ffa-faa41b884cd3
code: |
  numbers = [1, 2, 3, 4, 5, 6]

  while len(numbers) > 0:
    num = numbers.pop()
    print(num)

--- |
  `.remove()` can remove an item from the list.
---
type: live-code
id: 2fbc45fd-7814-4d10-82b7-cc019792fa17
code: |
  numbers = [2, 4, 5, 6, 8, 10]

  # remove the odd one out
  numbers.remove(5)

  print(numbers)

---
type: categorization-question
id: 5688abb1-dd96-4eae-aff3-8955c35e34ca
question: |
  You can find the various methods supported by a list in the [reference documents](https://docs.python.org/3/tutorial/datastructures.html). Based on this document, choose the method that would perform the desired operation.
mappings:
  "Method for appending items from one list to another": ".extend()"
  "Method for remove all items from a list": ".clear()"
  "Method for reversing the order of items in a list": ".reverse()"
