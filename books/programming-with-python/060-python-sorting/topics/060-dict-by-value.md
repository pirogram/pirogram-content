title: Dict By Value
--- |
  We earlier saw how to iterate through the items of a dictionary as if the keys were sorted:

---
type: live-code
id: 3fdf04de-d888-4ec7-b129-cac4d5968f76
code: |
  fruit_basket = {'apple': 4, 'peach': 9, 'banana': 2, 'pineapple': 3, 'kiwi': 6}

  for fruit_name in sorted(fruit_basket):
    print(fruit_name, '->', fruit_basket[fruit_name])

--- |
  What if we want to iterate through these items such that they are sorted by value? For example, we want to first print the fruit with least quantity and eventually, the fruit with max quantity?

  Let's build up for that. First, remember that `dict.items()` lets us iterate over `(key, value)` as a tuple.

---
type: live-code
id: 5e314dc2-dfa0-41a5-872a-9a0f57b5b35b
code: |
  fruit_basket = {'apple': 4, 'peach': 9, 'banana': 2, 'pineapple': 3, 'kiwi': 6}

  for item in fruit_basket.items():
    print(item)

--- |
  Now, we can wrap up `fruit_basket.items()` within `sorted()`.

---
type: live-code
id: d61bcd4a-45c5-4088-aa59-6c73ad57d192
code: |
  fruit_basket = {'apple': 4, 'peach': 9, 'banana': 2, 'pineapple': 3, 'kiwi': 6}

  from operator import itemgetter
  for item in sorted(fruit_basket.items(), key=itemgetter(1)):
    print(item)

--- |
  We can even unpack the key & value to print them properly.

---
type: live-code
id: d81e2e52-eedf-4e7e-b369-bbd39594721b
code: |
  fruit_basket = {'apple': 4, 'peach': 9, 'banana': 2, 'pineapple': 3, 'kiwi': 6}

  from operator import itemgetter
  for name, quantity in sorted(fruit_basket.items(), key=itemgetter(1)):
    print(name, '->', quantity)

--- |
  We can even do more fun things with this approach. For example, we can find out the fruit with max quantity in our basket.

---
type: live-code
id: 23ed43aa-bd8d-47a2-a3af-3fdc0b25d69b
code: |
  fruit_basket = {'apple': 4, 'peach': 9, 'banana': 2, 'pineapple': 3, 'kiwi': 6}

  from operator import itemgetter
  fruit_basket = sorted(fruit_basket.items(), key=itemgetter(1))

  fruit_basket[-1]

---
type: testless-coding-question
id: 08e4bbcc-eee6-4893-8424-a6b9a93ff3a1
question: |
  Ask the user to enter multiple numbers separated by space (` `) character. Print the number that occurs maximum number of times. For example, if the user entered `4 2 4 3 9 2 2`, the program would print:
  ```
  2 was entered most often.
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: 5967cbaf-3fc1-40f1-8aa3-12850e7c2f51
question: |
    Ask the user to enter a sentence. Print the letter that occurs maximum number of times. For example, if user entered: `brown fox crazy dog sleepy fox jumpy dog`, the program would print:
    ```
    Letter o occurred 5 times.
    ```

    Note: you must ignore space character.
code: |
  # your code goes here.
