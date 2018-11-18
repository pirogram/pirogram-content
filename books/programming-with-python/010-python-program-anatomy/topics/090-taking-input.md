title: Taking Input
--- |
  Very often in your program, you would ask the user to enter a string or a number. This is especially true for some of the initial programs that you would write. Python provides a function to take user's input and (unsurprisingly!) it's called `input()`. Here is how it works:

---
type: live-code
id: d61324d1-b0cd-4c52-9475-176b04a43b0b
code: |
  name = input("What's your name? ")
  print('Hello', name)

--- |
  Remember, `input()` yields a value of `str` type. You would usually store it in a variable and then do something with it in subsequent statements.

---
type: testless-coding-question
id: 22d31c38-b4ec-4c67-8b6c-19cdc54169d1
question: |
  Ask the user to enter to his/her name. Print a statement appreciating the name. For example, if the user entered `Spiderman`, the program would print `Spiderman? That is a nice name.`
code: |
  # your code goes here.

---
type: testless-coding-question
id: 0d460113-26a1-40db-8cc1-fc3d4647b379
question: |
  Ask the user to enter his/her favorite food. Print a statement saying that you also like that food. For example, if the user entered `donut`, the program would print `I also love donut.`
code: |
  # your code goes here
