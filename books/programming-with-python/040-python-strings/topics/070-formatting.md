title: Formatting
--- |
  Formatting strings in Python is simple and intuitive.

---
type: live-code
id: cab772e0-61dc-48f8-926b-03b482596e59
code: |
  name = 'James Bond'

  greeting = f'Hello {name}'
  greeting

---
type: live-code
id: 8a15146c-279d-45f7-a66d-91bbc7e55643
code: |
  numbers = [1, 2, 3, 4]

  s = f'Sum of numbers is {sum(numbers)}'
  s

---
type: live-code
id: 79082993-0a4a-461f-a02c-5f4676a999a3
code: |
  closet = {"shirts": 16, "jeans": 5}

  s = f'I have {closet["shirts"]} shirts and {closet["jeans"]} jeans in my closet.'
  s
