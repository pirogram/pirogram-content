title: Variable Named Arguments
--- |
  There are many ways to pass arguments to a function. Let's look at them in the context of a simple function. This function takes two numbers as argument and subtracts 2nd number from 1st number.

---
type: live-code
id: 0142aad0-9c3f-49e7-99c0-a87a586cbec9
code: |
  def subtract(num1, num2):
    return num1 - num2

---
type: live-code
id: 1e6d8655-bb77-4e82-a4fc-1c7906379eb0
code: |
  subtract(5, 3)

---
type: live-code
id: 7c4b2911-fbc2-4a2e-837e-c890a69951e0
code: |
  subtract(num1=5, num2=3)

---
type: live-code
id: 483c953b-e500-4b90-afc7-73a54191e9f5
code: |
  subtract(5, num2=3)

---
type: live-code
id: 1e8ef236-3c60-41ef-b5f1-e30ff8a2c4d2
code: |
  subtract(num2=3, num1=5)

--- |
  ## `**kwargs`
  A function can choose to accept variable number of keyword arguments. Example:

---
type: live-code
id: a0b92506-dfc6-4c12-9cc2-8078c1080982
code: |
  def closet(**kwargs):
    for k, v in kwargs.items():
      print(k, '->', v)

  closet(shirts=5, shorts=2, t_shirts=3, shoes=4)

--- |
  A good real life example of using `kwargs` is creation of dictionary.

---
type: live-code
id: d6233b80-a1f2-49e4-83bb-787864a72b70
code: |
  d = dict(eggs=2, bread=3, milk=1)
  d

--- |
  In later sections, we'll solve some problems where `kwargs` would come in handy. For now, it's sufficient to just understand this concept.
