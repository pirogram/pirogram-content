title: Organizing Values as List
--- |
  Let's say, we are working on a Windows Explorer or Mac Finder kind of application that shows a list of files in a folder. We would hold all the file names in a list:
---
type: live-code
id: 33b07fd0-1c3e-4325-8f74-f9d45df622a6
code: |
  files = ['students.xls', 'expenses.xls', 'lease.doc', 'todo.txt']

  print(files)
--- |
  In this example, we created a list of files. Each filename was separated by comma (`,`) and surrounded by `[]`. This is pretty much how you create a list. Take a bunch of values, separate them by comma, surround them by `[]` and you are done.

  If you think about it, a list is also a type of value. List is also called a data structure since it binds data (or values) in a structure. In this case, we took four individual values (`'students.xls'`, `'expenses.xls'`, `'lease.doc'` and `'todo.txt'`) and put them in a list structure. All this will become clearer as we go along.

  Let's create another list. We tossed a coin 8 times and recorded the outcomes in a list:
---
type: live-code
id: 32f473bc-b8d9-4af5-b633-5047d373a221
code: |
  toss_outcomes = ['H', 'H', 'T', 'H', 'T', 'T', 'T', 'H']

  print(toss_outcomes)
--- |
  An important thing about coin toss is that there is a sense of _order_ within the outcomes. We do want to remember whether the 2nd toss gave us heads or tails. And as you would notice from the `print(toss_outcomes)` statement, the list preserves the order of values. It's a very important thing about lists.

  A list can have values of different types. For example, here is a list that mixes up numbers and strings.

---
type: live-code
id: 1779438f-946d-48e1-ba68-ff036ee2fdea
code: |
  mixed_up = ['i', 'have', 3, 'choices']
  print(mixed_up)
--- |
  In fact, you can also make a list of lists (and so on):
---
type: live-code
id: 4d35b1b8-909f-42cf-800e-00d20b0a0385
code: |
  list_of_lists = [
    [1, 2, 3],
    ['one', 'two', 'three'],
    ['uno', 'dos', 'tres']
  ]

  print(list_of_lists)
---
type: testless-coding-question
id: 9a7b6a82-ffc3-4515-9bf0-030e78b5ae75
question: |
  Here is a simple exercise to make you comfortable with creating lists. Think of any 4 numbers between 1 and 100 and store them in a list.
code: |
  numbers = # your code goes here

  print(numbers)
