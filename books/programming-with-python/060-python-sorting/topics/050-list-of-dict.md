title: List of Dictionaries
--- |
  We often run into a problem where we should sort a list of dictionaries. For example, the following code sorts a list of emails based on `From` field.

---
type: live-code
id: de63a48b-9929-4aa6-aa99-92fcd8920774
code: |
  emails = [
    {'From': 'Superman', 'To': 'Batman', 'Subject': 'Hi There!'},
    {'From': 'Batman', 'To': 'Superman', 'Subject': 'Re: Hi There!'},
    {'From': 'Joker', 'To': 'Batman', 'Subject': 'Wanna Play?'},
    {'From': 'Batman', 'To': 'Joker', 'Subject': 'Re: Wanna Play?'},
  ]

  def extract_from(email):
    return email['From']

  sorted(emails, key=extract_from)

--- |
  This need is so common that there is a built-in function we can use for this.

---
type: live-code
id: 2fc18ceb-becc-4173-85de-61e6d4fa3e43
code: |
  emails = [
    {'From': 'Superman', 'To': 'Batman', 'Subject': 'Hi There!'},
    {'From': 'Batman', 'To': 'Superman', 'Subject': 'Re: Hi There!'},
    {'From': 'Joker', 'To': 'Batman', 'Subject': 'Wanna Play?'},
    {'From': 'Batman', 'To': 'Joker', 'Subject': 'Re: Wanna Play?'},
  ]

  from operator import itemgetter

  sorted(emails, key=itemgetter('From'))

---
type: testless-coding-question
id: f84c0d37-e236-4743-b409-9e0f10101995
question: |
  Given the following list of emails (as dictionary), sort them by `To` field.
code: |
  emails = [
    {'From': 'Superman', 'To': 'Batman', 'Subject': 'Hi There!'},
    {'From': 'Batman', 'To': 'Superman', 'Subject': 'Re: Hi There!'},
    {'From': 'Joker', 'To': 'Batman', 'Subject': 'Wanna Play?'},
    {'From': 'Batman', 'To': 'Joker', 'Subject': 'Re: Wanna Play?'},
  ]

  # your code goes here

---
type: testless-coding-question
id: f84c0d37-e236-4743-b409-9e0f10101995
question: |
  Given the following list of emails (as dictionary), sort them by `Subject` field.
code: |
  emails = [
    {'From': 'Superman', 'To': 'Batman', 'Subject': 'Hi There!'},
    {'From': 'Batman', 'To': 'Superman', 'Subject': 'Re: Hi There!'},
    {'From': 'Joker', 'To': 'Batman', 'Subject': 'Wanna Play?'},
    {'From': 'Batman', 'To': 'Joker', 'Subject': 'Re: Wanna Play?'},
  ]

  # your code goes here
