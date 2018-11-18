title: Conditional Operators
--- |
  We'll now look at another category of operators called conditional operators. They check whether certain conditions are `True` or `False`. For example:
---
type: live-code
id: 8adb77fd-1be6-48ad-8858-4843bdf0f982
code: |
  4 > 2
---
type: live-code
id: af5e5045-f7a9-4760-9f29-eeda5bd04829
code: |
  2 > 4
--- |
  The `>` operator took two values and told us whether the value on left was greater than the value on right or not. This operator takes two values and gives us `True` or `False`. `True/False` are special type of values in Python and we call them `boolean` values or `boolean` data type.

  In the following coding box, try out each of the following operators:
  * `>`
  * `<`
  * `>=`
  * `<=`
  * `==`
  * `!=`

---
type: live-code
id: 7d1a73bd-165e-4136-97c0-02be0cf9d7b5
code: |
  # try out code here.
--- |
  We saw that you could join multiple mathematical operations in a single statement as follows:
---
type: live-code
id: bda9f208-2b9e-4ff0-a5e4-365c72444ad0
code: |
  (4 + 2) * (3 - 1)
--- |
  How do you join multiple conditional operations? Using `and` & `or`.
---
type: live-code
id: 6376cc67-a986-4d25-9a18-32e23e4b9bec
code: |
  (4 > 2) and (3 > 1)
---
type: live-code
id: 85a9a9ab-6b51-468f-be35-3cf78dd9fd19
code: |
  (2 == 2) or (1 > 10)

--- |
  `and` & `or` operators take two boolean values (`True/False`) and yield a boolean value. How do they work? `and` yields `True` if both the values are `True`; if even one of the values is `False`, it yields `False`. On the other hand, `or` yields `True` if any of the values is `True`. It yields `False` only if all values are `False`.

  To try out their behavior, try supplying various combinations of `True` and `False` to `and` & `or` operators.
---
type: live-code
id: aba61255-f2e4-4a66-ba70-677311e205ce
code: |
  True and True
---
type: live-code
id: 9c5a431c-737d-4f08-8c7f-29156a7abbc7
code: |
  False or False

--- |
  You can also use multiple `and`/`or` in a single statement. The following would yield `True` if all are `True`. Try playing with the following code snippets. Modify various expressions so that they return `True/False`.
---
type: live-code
id: 29adbf26-8f51-4c56-8b30-ec7757bdb186
code: |
  (4 == 4) and (2 < 3) and (4 > 2)

---
type: live-code
id: 1d86faeb-c0ed-40f0-8400-b44326f5bc44
code: |
  (4 != 4) or (9 < 3) or (3 < 1)
  
---
type: categorization-question
id: 5124eaf6-70ff-4dd6-833e-727d91b187f2
question: |
  Can you select whether the following statements would yield `True` or `False`?
mappings:
  "4 <= 4": "True"
  "(4 == 4) and (5 == 4)": "False"
  "(4 == 4) or (5 == 4)": "True"
  "(4 <= 4) and ((5 == 4) or (2 < 4))": "True"
