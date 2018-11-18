title: Comprehension With Filtering
--- |
  What if we don't want to transform a list of numbers such that we keep only `+ve` numbers from the list and discard all the `-ve` numbers?

---
type: live-code
id: 19c844ce-245b-4fa4-8990-9d89d07faf33
code: |
  numbers = [1, -1, 0, -20, 31, -4, 6]

  pos_numbers = [num for num in numbers if num >= 0]

  pos_numbers

--- |
  This kind of example may look silly. So, here is another example. We have a list of emails. We want to create a list of emails that came from `Superman`. Here is a quick one for that.

---
type: live-code
id: 57e42c59-b4a4-4b50-97a0-26a2fd47ad2e
code: |
  emails = [
    {'from': 'Superman', 'Subject': 'Flying High'},
    {'from': 'Batman', 'Subject': 'Where is Joker?'},
    {'from': 'Superman', 'Subject': 'Need Another Cape'},
    {'from': 'Spiderman', 'Subject': 'Climbing the Wall'},
  ]

  emails_from_superman = [email for email in emails if email['from'] == 'Superman']

  emails_from_superman

---
type: testless-coding-question
id: cd81269c-bb0c-4133-abce-7dcdcb1194e8
question: |
  Out of a list of numbers, create another list that has only `-ve` numbers.
code: |
  numbers = [1, -1, 0, -20, 31, -4, 6]

  # your code goes here

---
type: testless-coding-question
id: 0c719dfe-4e3e-4329-bc2c-423d24cdba79
question: |
  Out of a list of numbers, create another list that has only odd numbers from the original list.
code: |
  numbers = [1, 2, 3, 4, 5, 6, 7, 8]

  # your code goes here

---
type: testless-coding-question
id: 5a73c6cd-bd20-43f9-89e1-4d5b312f0066
question: |
  Given height related data in a list form, extract names of people whose height is greater 150cm. For this example, the list should be `['Jagga Jasoos', 'James Bond']`.
code: |
  heights = [
    {'name': 'Jagga Jasoos', 'height': 153},
    {'name': 'James Bond', 'height': 160},
    {'name': 'Spiderman', 'height': 149}
  ]

  # your code goes here

---
type: testless-coding-question
id: 7c725223-b70e-4cf9-8bd7-7a36e98aa7a6
question: |
  Given account balance related data in a list form, extract account numbers whose balance is in negative.
code: |
  accounts = [
    {'account_number': 1432, 'balance': 40},
    {'account_number': 8324, 'balance': 44},
    {'account_number': 9214, 'balance': -23},
    {'account_number': 3242, 'balance': -7},
  ]

  # your code goes here
