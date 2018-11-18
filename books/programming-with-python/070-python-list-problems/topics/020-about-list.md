title: About List
--- |
  This section has a couple of problems where you need to find out something about a given list. For example, the following function finds the 2nd largest number in a list.

---
type: live-code
id: 767d8077-52dd-4983-b117-67767cfac3a0
code: |
  def get_second_largest(numbers):
    if len(numbers) < 2: return None

    numbers = sorted(numbers)
    return numbers[-2]

  get_second_largest([2, 9, 2, 3, 91])
--- |
  Another solution that does not use sorting. We have to track two largest numbers that we have seen so far.

---
type: live-code
id: 2b9f47bc-fb86-4be1-abdd-cf84802df5dd
code: |
  def get_second_largest(numbers):
    if len(numbers) < 2: return None

    if numbers[0] > numbers[1]:
      largest, second_largest = numbers[0], numbers[1]
    else:
      largest, second_largest = numbers[1], numbers[0]

    for n in numbers[2:]:
      if n > largest:
        largest, second_largest = n, largest
      elif n > second_largest:
        second_largest = n

    return second_largest

  get_second_largest([2, 9, 2, 3, 91])

---
type: coding-question
id: 6ffbd944-b0d7-4c2e-8427-a5c8082c2096
question: |
  Write a function `get_second_smallest(numbers)` that takes a list of numbers as argument. It returns the second smallest number from the list. You can sort the list to find the second smallest number.
code: |
  # your code goes here
tests: |
  assert get_second_smallest([2, 9, 2, 3, 91]) == 2
  assert get_second_smallest([4, 3, 8, 2]) == 3
  assert get_second_smallest([4, 3, 8, 2, 1]) == 2
  assert get_second_smallest([4]) == None

---
type: coding-question
id: 1f06145c-cc38-4311-a5b9-3bc6a8f4e833
question: |
  Write a function `get_second_smallest(numbers)` that takes a list of numbers as argument. It returns the second smallest number from the list. Do not sort the list.
code: |
  # your code goes here
tests: |
  assert get_second_smallest([2, 9, 2, 3, 91]) == 2
  assert get_second_smallest([4, 3, 8, 2]) == 3
  assert get_second_smallest([4, 3, 8, 2, 1]) == 2
  assert get_second_smallest([4]) == None

---
type: coding-question
id: bf93a5f3-1550-4d5e-9ebf-fa5db63f0fd6
question: |
  Write a function `kth_smallest(numbers, k)` that takes two inputs: a list of `numbers` and `k` is a number which is greater than `0`. It returns the `kth` smallest element from the list. You can sort the list to solve this problem.
code: |
  # your code goes here
tests: |
  assert kth_smallest([2, 9, 2, 3, 91], 4) == 9
  assert kth_smallest([2, 9, 2, 3, 91], 5) == 91
  assert kth_smallest([2, 9, 2, 3, 91], 6) == None
  assert kth_smallest([], 1) == None

---
type: coding-question
id: 1d6a0b9c-24cb-4a83-82f5-f196bfd70ab3
question: |
  Write a function `lists_are_equal(l1, l2)` that takes two lists as arguments. It returns `True` if all elements in `l1` & `l2` are same. `False` otherwise. Do not use the `==` operator to check list equality. Iterate through the list and check if all elements within the lists are equal.
code: |
  # your code goes here.
tests: |
  assert lists_are_equal([1, 2, 3], [1, 2, 3]) == True
  assert lists_are_equal([3, 2, 1], [3, 2, 1]) == True
  assert lists_are_equal([3, 2, 1, 3], [3, 2, 1, 3]) == True
  assert lists_are_equal([3, 2, 1, 3], [3, 3, 2, 1]) == False
  assert lists_are_equal([1, 2, 3], [1, 2, 4]) == False
  assert lists_are_equal([1, 2, 3], [1, 2]) == False
  assert lists_are_equal([1, 2], [1, 2, 3]) == False
  assert lists_are_equal([2, 3], [1, 2, 3]) == False
  assert lists_are_equal([1, 2, 3], [2, 3]) == False
  assert lists_are_equal([1, 2, 3], [2, 2, 3]) == False
