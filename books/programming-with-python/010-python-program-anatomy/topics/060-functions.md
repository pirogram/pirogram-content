title: Functions
--- |
  Functions are special kind of operators. They also take a bunch of values and yield some other value. Functions have a slightly different syntax:
---
type: live-code
id: f5e73992-1e86-4498-a91e-cca63adfac57
code: |
  print('Hello World')
--- |
  The `print` function took the value `Hello World` and printed it. You can also put expressions in the function call:
---
type: live-code
id: e71b1e7c-6e11-4235-8d5c-4bcf6c53febd
code: |
  print('Hello' + ' ' + 'World')
--- |
  In this case, the string concatenation operations are evaluated first and then the resultant value is given to `print` function. You can also pass multiple values to `print`:
---
type: live-code
id: 852cb0f8-258e-4ddd-9a20-267a976355e3
code: |
  print('Hello', 'World')
--- |
  In this case, the `print` function concatenates them and prints the final value. Here are the visualizations of Abstract Syntax Trees (ASTs) for these code snippets:

  ![AST](assets/img/ast2.svg)

  The main thing here is not what `print` function does. The main thing is that you can think of functions as special kind of operators which take some values, do something with those values and _may_ yield another value. Python itself comes with a large collection of functions and most importantly, you can write your own functions. We'll do that later in the course of learning Python.

  Let's look at another function:
---
type: live-code
id: 412e76b8-fcd5-4581-a080-a3c3c5897fae
code: |
  # yield the largest number
  max(4, 3, 9, 20)

--- |
  You can use multiple functions in a single statement:

---
type: live-code
id: 81a23055-3d0f-40b9-b6c1-bd51c0a8bd83
code: |
  print( max(4, 3, 2, 1) )

---
type: testless-coding-question
id: b6cdbc48-01ed-400d-80ff-c1ce1f5ae098
question: |
  Using the `print` function, print `Hi There!`.
code: |
  # your code goes here
