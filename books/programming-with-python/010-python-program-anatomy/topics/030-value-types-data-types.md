title: Value Types / Data Types
--- |
  The values can be of different types. So far, we worked with numbers but that's just the starting. In fact, even numbers come in various types. We'll now study some of these types. In programming language parlance, these types are called `data types` (and not _value types_).

  We'll look at two types of numbers: `int` (integer) and `float` (floating point). `1`, `4`, `20003` are examples of `int`. `4.3`, `3.9`, `1.0` are examples of `float`. Even though, `1` and `1.0` may be same in the underlying value but they are two different data types. When you give them to an operator, the value coming out of the operator may be different. Checkout the following examples to understand how operators may be behave differently for different data types:

---
type: live-code
id: a2d44c36-d46f-4634-9c9c-c350a62c0266
code: |
  4 * 5
---
type: live-code
id: deba4a04-6582-4cfc-922c-84a1d7bc39bb
code: |
  4.0 * 5
---
type: live-code
id: 623fb7a2-077f-4323-9535-c7c4b857c8a0
code: |
  4.0 * 5.0
--- |
  Can you tell the difference between the behavior of `*` operator in aforementioned examples?

  Programming would be very boring if we could only work with numbers. The other data type we'll look at is called `str` (string, text etc). `'Hello'`, `'World'`, `'Singapore'`, `'Temperature'` are examples of string data type. Note: the string values are enclosed within quotation marks (`''`).

  What happens when pass two strings to `+` operator?
---
type: live-code
id: 34e5b287-29d6-48fb-8c5c-050f4c58ce3c
code: |
  'He' + 'llo'
--- |
  `+` operator is intelligent. When it's given two numbers, it adds them together but when it's given two strings, it concatenates them. What happens when you give it a string and a number?

---
type: live-code
id: 8d7c07f7-81e4-4b56-bc70-9f3ba761ffa4
code: |
  'He' + 4
--- |
  Well, it doesn't know what to do in this situation. So, it decides to throw an error.

  How about the `*` operator? What does it do with strings?

---
type: live-code
id: 8a6f6fac-072c-4159-870b-a47f738d3149
code: |
  'He' * 'llo'
---
type: live-code
id: 62118b47-e865-40eb-b060-1d1322e65389
code: |
  'He' * 4
--- |
  As you would notice, each operator makes its own decision about what to do with the values it receives. `+` operator works with two strings but not a string and a number. On the other hand, `*` operator works with a string and a number but not with two strings.

---
type: testless-coding-question
id: 51e1af43-6924-4fcd-95e6-181cb424f021
question: |
  See what happens when you give two strings to `-` operator.
code: |
