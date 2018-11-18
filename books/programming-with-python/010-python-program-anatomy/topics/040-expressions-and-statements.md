title: Expressions and Statements
--- |
  English language has a few building blocks like nouns, pronouns, verbs etc. These building blocks form sentences that form paragraphs etc. In Python, the building blocks (i.e. values and operators) form expressions. These expressions form statements. Let's understand through examples:

---
type: live-code
id: 8ed15b44-6ee6-4da7-981c-bb7a50a47287
code: |
  4 + 2
--- |
  Here, `4` and `2` are the values, `+` is the operator. `4 + 2` itself is an expression. Here is another example:

---
type: live-code
id: fe7a4065-de62-4c28-b8b7-90bf8c46b409
code: |
  (4 + 2) * (3 - 1)
--- |
  This example has 3 expressions: `4 + 2`, `3 - 1` and another one that takes the result  of `(4 + 2)` and `(3 - 1)` and multiplies them. Here is a quick way to visualize these three expressions. This kind of visualization is called _Abstract Syntax Tree (AST)_.

  ![AST](assets/img/ast1.svg)

  Even though these are three expressions, it is still one statement. One way to think about it is that all expressions within a statement are connected (i.e. the values flow around) but expressions in different statements are disconnected.

---
type: fill-in-the-blank-question
id: 95cd83d6-2dea-4ebf-b5f6-31bdb111bd4d
question: |
  How many expressions are there in the following statements?
blanks:
  - label: "(3 - 2) * 1.0"
    answer: 2
  - label: "(2 + 4) - (4 + (3 - 1))"
    answer: 4
