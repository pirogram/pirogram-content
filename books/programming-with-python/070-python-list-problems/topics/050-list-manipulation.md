title: List Manipulation
--- |
  It's very common to run into problems that require you to manipulate lists. It could be about swapping the elements or moving them around in some other way.

  Here is an example. Let's say, we have a list of numbers. We want to move all odd numbers to the beginning of the list and all even numbers to the end. Note: we don't want to create a new list. We want to update the current list by moving the elements around. How do we do that?

---
type: live-code
id: ac9667f2-808b-4d84-a0fe-14858e710029
code: |
  def odd_even_sorter(numbers):
    curr_even_index = None

    for index in range(len(numbers)):
      if numbers[index] % 2 == 0:
        if curr_even_index is None:
          curr_even_index = index
      else:
        if curr_even_index is not None:
          numbers[curr_even_index], numbers[index] = \
            numbers[index], numbers[curr_even_index]
          curr_even_index += 1

    return numbers

  odd_even_sorter([1, 2, 3, 4, 5, 6])

---
type: coding-question
id: 12cf615f-b00b-4f25-b42a-52c0ffb4e5fa
question: |
  Write a function `sign_sorter(numbers)` that takes a list of numbers as an input. It moves all the `-ve` numbers to the beginning of the list and all `+ve` numbers to the end of the list. Consider `0` to be a `+ve` number. It returns the modified list.
code: |
  # your code goes here
tests: |
  assert sign_sorter([-1, 1, -2, -3, 4, -4]) == [-1, -2, -3, -4, 1, 4]
  assert sign_sorter([1, -2, -3, 4, -4]) == [-2, -3, -4, 1, 4]
  assert sign_sorter([-1, 1, -2, -3, 0, 4, -4]) == [-1, -2, -3, -4, 1, 0, 4]

---
type: coding-question
id: d1238620-ae24-4301-8a11-7b8d4810af9f
question: |
  Write a function `reverse(items)` that takes a list as an input. It reverses the order of items in the list. For example, `[1, 2, 3, 4, 5]` would become `[5, 4, 3, 2, 1]`. Return the modified list.
code: |
  # your code goes here
tests: |
  assert reverse([1, 2, 3, 4, 5]) == [5, 4, 3, 2, 1]
  assert reverse([1, 2, 3, 4, 5, 6]) == [6, 5, 4, 3, 2, 1]
  assert reverse([1, 2, 3]) == [3, 2, 1]
  assert reverse([1, 2]) == [2, 1]
  assert reverse([1]) == [1]
  assert reverse([]) == []

---
type: coding-question
id: 1778f6a9-03ce-4bc9-b979-c021dff6c7cd
question: |
  Write a function `running_total(numbers)` that takes a list of numbers as an argument. It updates the list to replace actual numbers by running total. For example, `[1, 2, 3, 4, 5]` would become `[1, 3, 6, 10, 15]`. It returns the modified list.
code: |
  # your code goes here
tests: |
  assert running_total([1, 2, 3, 4]) == [1, 3, 6, 10]
  assert running_total([4, 3, 2, 1]) == [4, 7, 9, 10]

---
type: coding-question
id: 325daf1c-9eb2-4d70-97c2-479db0cfe4f4
question: |
  Write a function `rotate(items)` that takes a list of items as input. It rotates the list by 3 elements. For example, if the input is `[1, 2, 3, 4, 5, 6, 7, 8]`, it would become `[6, 7, 8, 1, 2, 3, 4, 5]`. It returns the modified list.
code: |
  # your code goes here
tests: |
  assert rotate([1, 2, 3, 4, 5, 6, 7, 8]) == [6, 7, 8, 1, 2, 3, 4, 5]

---
type: coding-question
id: c6cc1774-94d8-4bc3-b60c-c5f64661a3e7
question: |
  Write a function `bubble_sort(numbers)` that takes a list of numbers as input and sorts them using the [bubble sort algorithm](https://en.wikipedia.org/wiki/Bubble_sort#Step-by-step_example).
code: |
  # your code goes here
tests: |
  assert bubble_sort([4, 3, 7, 9, 1]) == [1, 3, 4, 7, 9]
