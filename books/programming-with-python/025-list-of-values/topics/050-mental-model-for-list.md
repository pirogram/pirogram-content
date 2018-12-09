title: Mental Model for List
--- |
  It's a good time for us to take a step back and develop a fresh mental model about lists. What exactly is a list? What is its structure? When we look at a list like `[40, 30, 50, 90, 70]` or `['apple', 'orange', 'banana', 'kiwi', 'guava']`, we may feel that it's a bunch of items thrown together in a collection. But there is more to it than meets the eye. We'll use the following illustration to understand the anatomy of a list.

  ![list anatomy](assets/img/list-anatomy.svg)

  We have already worked with values, forward indexing and reverse indexing in the context of a list. We'll now introduce the concept of a `slot`.

  So far, we looked at the list as a sequence of _values_. While that mental model works for the most part, it's over-simplified. The correct mental model is to see a list as a sequence of slots and each slot holds a value for us.

  In this example, the list of fruits has 5 slots. The slots are numbered 0 to 4 in the forward direction (or -1 to -5 in the reverse direction). Each slot could carry a value. It could be any value. The slots in this list happen to have certain values. What happens when you run the following code?

---
type: live-code
id: ce7578d0-6d0a-4de3-b879-3fc3cb4b6448
code: |
  fruits = ['apple', 'orange', 'banana', 'kiwi', 'guava']

  fruits[1] = None
  fruits
--- |
  You can visualize this operation as per the following illustration:

  ![list anatomy none](assets/img/list-anatomy-none.svg)

  Slot at index 1 is now empty. But the slot is still there!

  What happens if you reassign the value at index 1 (as in the following code)?
---
type: live-code
id: ea7a3cee-a7f4-4212-a99f-eb1924efd03c
code: |
  fruits = ['apple', 'orange', 'banana', 'kiwi', 'guava']

  fruits[1] = 'pineapple'
  fruits
--- |
  It's akin to following:

  ![list anatomy replacement](assets/img/list-anatomy-replacement.svg)

  The item presently at index 1 is thrown away and a different item is placed in the slot.
