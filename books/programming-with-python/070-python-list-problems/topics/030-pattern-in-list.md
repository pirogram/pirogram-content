title: Pattern in List
--- |
  This topic is about identifying whether the elements in the list follow a given pattern or not.

  Example, this function returns `True` if the given list of numbers forms an [arithmetic progression](https://en.wikipedia.org/wiki/Arithmetic_progression). Otherwise, it returns `False`.

---
type: live-code
id: 7b69e4d2-dbd3-4054-a990-4d1acdc238f5
code: |
  def is_arithmetic_progression(numbers):
    if len(numbers) <= 2: return True

    diff = numbers[1] - numbers[0]
    for index in range(2, len(numbers)):
      if numbers[index] - numbers[index-1] != diff:
        return False

    return False

  is_arithmetic_progression([1, 3, 5, 7, 9])

---
type: coding-question
id: eea39b95-de0a-4ab1-9490-7bd3552d7cff
question: |
  Write a function `same_elements(l)` that takes a list as an argument. It returns `True` if all elements within the list are same. Otherwise, it returns `False`
code: |
  # your code goes here
tests: |
  assert same_elements([1, 1, 1, 1]) == True
  assert same_elements([2, 1, 1, 1]) == False
  assert same_elements([1, 1, 1, 2]) == False

---
type: coding-question
id: 3f4dabc4-195a-4f2c-b695-fefe7ef33ac8
question: |
  Write a function `is_geometric_progression(numbers)` that takes a list of numbers as argument. It returns `True` if the numbers form a [Geometric Progression](https://en.wikipedia.org/wiki/Geometric_progression).
code: |
  # your code goes here
tests: |
  assert is_geometric_progression([3, 6, 12, 24, 48]) == True
  assert is_geometric_progression([3, 6, 12, 24, 24]) == False
  assert is_geometric_progression([3, 6]) == True

---
type: coding-question
id: 10718a2e-24ed-4836-9917-ad78f5ed9541
question: |
  Write a function `is_fibonacci_sequence(numbers)` that takes a list of numbers as argument. It returns `True` if the numbers form a [Fibonacci Sequence](https://en.wikipedia.org/wiki/Fibonacci_number).
code: |
  # your code goes here
tests: |
  assert is_fibonacci_sequence([1, 1, 2, 3, 5, 8, 13, 21, 34, 55]) == True
  assert is_fibonacci_sequence([1, 2, 3, 5, 8, 13, 21, 34, 55]) == False
  assert is_fibonacci_sequence([1, 1, 2, 3, 5, 8, 13, 21, 30]) == False

---
type: coding-question
id: 9a51365a-a924-4388-b514-edc5e173ae3c
question: |
  Write a function `has_duplicates(items)` that takes a _sorted_ list of items as argument. It returns `True` if this list has duplicate items. `False` otherwise.

  Hint: an easy way is to find if any of the two adjancent items are equal.
code: |
  # your code goes here
tests: |
  assert has_duplicates([1, 2, 3, 4, 5]) == False
  assert has_duplicates([1, 2, 2, 3, 4]) == True
  assert has_duplicates([1, 1, 2, 3, 4]) == True
  assert has_duplicates([1, 2, 3, 4, 4]) == True

---
type: coding-question
id: 7b596859-5b6c-40e7-94e2-5b4d4b450836
question: |
  Write a function `is_palindrome(word)` which takes a word as input. It returns `True` if the word is a palindrome. `False` otherwise.

  Note: you need to traverse the word from both the directions (beginning to middle and end to middle) while comparing 1st character with last, 2nd character with 2nd last, so on so forth.
code: |
  # your code goes here
tests: |
  assert is_palindrome('xerox') == True
  assert is_palindrome('ana') == True
  assert is_palindrome('anna') == True
  assert is_palindrome('dog') == False
  assert is_palindrome('anabna') == False
