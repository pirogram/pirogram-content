title: Conditional Transformation
--- |
  Let's say, we have a list of numbers. We would like to transform all even numbers to `0` and all odd numbers to `1`. For example, `[1, 2, 3, 4, 5, 6]` should become `[1, 0, 1, 0, 1, 0]`.

  How do we do that with list comprehension?

---
type: live-code
id: e2ef2f5d-3f01-4f2a-aaf3-f32b9b2ca73d
code: |
  numbers = [1, 2, 3, 4, 5, 6, 7, 8]
  odd_even = [1 if num%2 == 1 else 0 for num in numbers]
  odd_even

--- |
  You should read the line 2 as follows:

  ```Python
  odd_even = [
    1 if num%2 == 1     # output 1 if num is odd
    else 0              # else output 0
    for num in numbers  # for each num in numbers
  ]
  ```

---
type: testless-coding-question
id: e9cc8920-a03e-4818-a8d7-81d9213276ca
question: |
  Given a list of numbers, create a list whose entries are `+ve` and `-ve`. For example, given `[-3, -2, -1, 0, 1, 2, 3]`, the transformed list is `['-ve', '-ve', '-ve', '+ve', '+ve', '+ve', '+ve']`.
code: |
  numbers = [-3, -2, -1, 0, 1, 2, 3]

  # your code goes here

---
type: testless-coding-question
id: 2e20eff1-bf56-4a85-b43d-0fcd3ebf3612
question: |
  Given a list of height measurements, we want to output `'tall'` for height greater than 150. Otherwise, we want to output `'not-tall'`.
code: |
  heights = [144, 153, 159, 132, 160]

  # your code goes here
