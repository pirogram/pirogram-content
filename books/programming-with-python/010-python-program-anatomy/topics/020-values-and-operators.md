title: Values and Operators
--- |
  First, we'll cover the two most fundamental building blocks of a programming language: `value` and `operator`. Let's understand this through an example program:

---
type: live-code
id: f3333a32-8f32-4e0c-9c59-0b5f7093a68a
code: |
  4 + 5

--- |
  This is a fully functional Python program. In this program, `4` & `5` are the values and `+` is an operator. When you run this program, you would get `9` as a result. What really happens is that the operator `+` takes the values `4` & `5` and turns them into another value `9`.

  Here is another example:

---
type: live-code
id: 909d5cd1-af39-427d-91cc-4ee5691be9ef
code: |
  4 * 5

--- |
  In this example, the operator is `*` (multiplication). This operator takes the values `4` & `5` and turns them into the value `20`.

  In a way, you can think of an operator as a machine. You put some values in the machine and out come some other values. For example, you put raw carrots in a juicer and it turns raw carrots into pulp and juice. You put bread in the toaster and the same bread comes out but it's toasted now. You put ink and paper in a printer and out comes a printed page.

  So, operators are machines in that sense. Let's look at another example:
---
type: live-code
id: 9c529267-bd5f-40b9-bf84-f70cfd0249a4
code: |
  5 - 4

--- |
  `-` is also an operator that subtracts the value on right hand side (RHS) from the value on left hand side (LHS); in this case, `4` and `5` respectively. Interesting thing with `-` operator is that `4 - 5` is not same as `5 - 4`. Whereas, for `*` & `+`, LHS and RHS do not matter.

---
type: testless-coding-question
id: a51dd22c-4937-4d99-ab8d-c4c6df6b3a4b
question: |
  Find out what the `/` operator does by writing some code. Try it with `4 / 2` and `5 / 2`.
code:

---
type: testless-coding-question
id: c2323c70-9dfe-4946-8c2b-3ca442dee484
question: |
  Find out what the `//` operator does by writing some code. Try it with `4 // 2` and `5 // 2`.
code:

---
type: testless-coding-question
id: f46a6ab9-f1ed-4d19-bcc5-0aff799fad03
question: |
  `**` is the _power to_ operator. `2**4` means 2 to the power of 4. Try it.
code:

---
type: testless-coding-question
id: a51dd22c-4937-4d99-ab8d-c4c6df6b3a4b
question: |
  `%` is the remainder operator. `m % n` means divide `m` by `n` and yield the remainder value. Try it.
code:
