title: Symbol Table
--- |
  Variables are the underpinnings of any program. So, it would be helpful to understand how Python maintains the symbol table where all variables and corresponding values are stored.

  Let's understand it through an example. What does this program print?
---
type: live-code
id: b0431b13-d768-4943-a519-19971a69c1e0
code: |
  num = 4
  print(num)
  num = 12
  print(num)
--- |
  On statement 1, the symbol table becomes:

  | Variable Name | Value |
  | - | - |
  | num | `4` |

  So, first `print(num)` statement would print 4. One statement 3 (i.e. `num = 12`), the symbol table becomes:

  | Variable Name | Value |
  | - | - |
  | num | `12` |

  So, the final `print(num)` would print 12.

  Let's look at another example:
---
type: live-code
id: d916032b-3453-4850-88bf-8c7ec855914f
code: |
  a = 4
  b = a
  a = 12
  print(a)
  print(b)

--- |
  What does this program print? Let's look at how the symbol table is evolves in this case. After `a = 4`, the symbol table looks as follows:

  | Variable Name | Value |
  | - | - |
  | a | `4` |

  After `b = a`, `b` variable is added to the symbol table:

  | Variable Name | Value |
  | - | - |
  | a | `4` |
  | b | `4` |

  Note: you would see the value `4` against `b` even though the statement said `b = a`. Assignment operator takes the expression right hand side and fully evaluates it to a value before it assigns that value to the variable on left.

  Now, after `a = 12`, the symbol table becomes:

  | Variable Name | Value |
  | - | - |
  | a | `12` |
  | b | `4` |

  Since the entry for `a` already existed, it gets modified. But `b` remains untouched.

---
type: fill-in-the-blank-question
id: 7cd7532a-e31c-442a-92f7-ba12d21b8837
question: |
  Once the following code has been executed, what's the value of variables?
  ```Python
  a = 12
  b = a + 9
  c = b
  a = 2
  ```
blanks:
  - label: a
    answer: 2
  - label: b
    answer: 21
  - label: c
    answer: 21

---
type: fill-in-the-blank-question
id: f4303562-0eb2-41e6-98e7-9640a2bbeb25
question: |
  Once the following code has been executed, what's the value of variables?
  ```Python
  a = 9
  b = a * 2
  c = b
  a = c
  ```
blanks:
  - label: a
    answer: 18
  - label: b
    answer: 18
  - label: c
    answer: 18
