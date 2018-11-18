title: Variables
--- |
  Let's say we did some complex calculation:
---
type: live-code
id: f67587fd-c26f-4eb8-a8c7-b3fe9af0f90c
code: |
  (4 + 2) * (3 -1)
--- |
  What we would like to do is take the result of this calculation and add 4 to the same. One way to do it is as follows:
---
type: live-code
id: bc860193-8a93-4a92-ab06-1f4a9fda85a5
code: |
  ( (4 + 2) * (3 - 1) ) + 4
--- |
  So, we modified the current statement to add 4 to our calculation. However, it would be nice if we could leave the calculation statement as it was and add `4` in another statement. This is where `variables` come in. Let's look at an example:
---
type: live-code
id: 333378b6-8d0a-4a6b-b510-f0a85423610e
code: |
  num = (4 + 2) * (3 -1)
  num + 4
--- |
  In the statement `num = (4 + 2) * (3 -1)`, `num` is a variable and `=` is  the assignment operator. Note: `=` is not same as `==`; former is the assignment operator while the latter is equality check operator.

  The assignment operator `=` takes a variable name on the left hand side and a value on the right hand side. Python now _assigns_ the RHS value to the variable name on the left hand side. The way it works is that Python maintains a table of variable names and their corresponding value. It's called `symbol table`. When the program starts, this table is empty. But after our first statement `num = (4 + 2) * (3 -1)` is executed, the table looks like the following:

  | Variable Name | Value |
  | - | - |
  | num | `12` |

  When the program executes `num + 4` statement, it finds a variable name. It looks up the symbol table to find the value of that variable name (which happens to be `12` now).

  Let's see what happens when you try using a variable that does not exist yet.
---
type: live-code
id: 204902cd-9d6b-47fe-b9cc-5534a298cd99
code: |
  num2 + 4

--- |
  When Python tries to execute this statement, it looks up the symbol table to find `num2`. Since this variable has not been defined yet, Python would throw an error.

  Many new programmers get confused between variable names and string value types. String values are enclosed in `'` or `"` quotes while the variables names are without quotes. For example, `num` is a variable name and `'num'` is a value of string type.

  Variables can have any value type as a value. For example:
---
type: live-code
id: 461d32e5-4a28-4606-8195-b040c04e8b31
code: |
  name = 'Superman'
  print(name)
--- |
  In this case, the symbol table would look like:

  | Variable Name | Value |
  | - | - |
  | name | `'Superman'` |

  Note: the string value is in `''` quotes.
---
type: testless-coding-question
id: b89dc90e-8e94-4f33-a9b3-1e4f5ec43eb6
question: |
  Save the results of calculation `9 * 42` in a variable named `num`. In another statement, add `22` to `num`. What's the result?
code: |
  # your code goes here
