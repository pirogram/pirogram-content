title: Todo List
--- |
  In this project, we'll build an application for keeping track of todo items.
---
type: testless-coding-question
id: 75eb78d8-0f3c-41b2-9f01-0cc9a623132f
question: |
  Write a small application to keep track of Todo items. The user can view the current list of todo items and add more. Here is how the interaction looks when you start the application.
  ```
  Current List of Todos:
  ======================
  There are no todos yet. Add one to get started.

  Add a Todo:
  ```

  And this is how it proceeds:
  ```
  Current List of Todos:
  ======================
  There are no todos yet. Add one to get started.

  Add a Todo: Go to Moon
  ---
  Current List of Todos:
  ======================
  1. Go to Moon

  Add a Todo: Shoot a star
  ---
  Current List of Todos:
  ======================
  1. Go to Moon
  2. Shoot a star

  Add a Todo:
  ```
code: |
  # your code goes here.

---
type: testless-coding-question
id: fcc0f7c6-c731-49f3-b68b-f25e3164a5de
question: |
  Update the todo list program to enable deletion of Todo items. Here is how the interaction looks now:
  ```
  Current List of Todos:
  ======================
  There are no todos yet. Add one to get started.

  Add a Todo: Go to Moon
  ---
  Current List of Todos:
  ======================
  1. Go to Moon

  Do you want to (A)dd a Todo or (D)elete a Todo (A/D)? A
  Enter a Todo: Shoot a star
  ---
  Current List of Todos:
  ======================
  1. Go to Moon
  2. Shoot a star

  Do you want to (A)dd a Todo or (D)elete a Todo (A/D)? D
  Which Todo do you want to delete (number please)? 1
  ---
  Current List of Todos:
  ======================
  1. Shoot a star

  Do you want to (A)dd a Todo or (D)elete a Todo (A/D)?
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: 655867d6-6e1d-40d7-8cc1-253e81f3a416
question: |
  Now, we'll also allow the user to mark a Todo as `done`. Here is how the interaction looks:
  ```
  Current List of Todos:
  ======================
  There are no todos yet. Add one to get started.

  Add a Todo: Go to Moon
  ---
  Current List of Todos:
  ======================
  1. Go to Moon

  (A)dd (D)elete or (M)ark as done (A/D/M)? A
  Enter a Todo: Shoot a star
  ---
  Current List of Todos:
  ======================
  1. Go to Moon
  2. Shoot a star

  (A)dd (D)elete or (M)ark as done (A/D/M)? M
  Which one to mark as done (number please)? 1
  ---
  Current List of Todos:
  ======================
  1. [Done] Go to Moon
  2. Shoot a star

  (A)dd (D)elete or (M)ark as done (A/D/M)? D
  Which one to delete (number please)? 2
  ---
  Current List of Todos:
  ======================
  1. [Done] Go to Moon

  (A)dd (D)elete or (M)ark as done (A/D/M)?
  ```
code: |
  # your code goes here
