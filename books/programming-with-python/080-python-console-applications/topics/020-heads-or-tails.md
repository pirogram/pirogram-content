title: Heads or Tails
--- |
  We'll build a small coin toss game.
  * We'll ask the user to guess whether the toss would give `heads` or `tails`.
  * Then we'll simulate a coin toss and tell the user the result of toss.
  * We'll continue to ask the user as long as the user wants to play.
  * And we'll keep score.

  This is how it would look like when we start the game:
  ```
  Number of right guesses: 0 out of 0.
  Heads or Tails (H/T)?
  ```

  Here is what happens next:
  * The user makes the guess.
  * We simulate a coin toss and let the user know result.
  * We update the score and ask for next choice.
  * When the user enters blank (`''`), program exits.

  ```
  Number of right guesses: 0 out of 0.
  Heads or Tails (H/T)? H
  Tossed the coin and result is .. T
  ---
  Number of right guesses: 0 out of 1.
  Heads or Tails (H/T)? H
  Tossed the coin and result is .. H
  ---
  Number of right guesses: 0 out of 1.
  Heads or Tails (H/T)?
  ```

  Here is the code for this game.

---
type: live-code
id: 0785e358-926f-466d-b44d-4df99a531ddb
code: |
  import random

  choices = ['H', 'T']

  correct_guesses = 0
  total_guesses = 0

  while True:
    print(f'Number of guesses: {correct_guesses} out of {total_guesses}.')
    guess = input('Heads or Tails (H/T)? ')

    # If the guess is not a valid choice, break out of loop and exit program.
    if guess not in choices:
      break

    # simulate coin toss.
    zero_or_one = random.randint(0, 1)
    toss = choices[zero_or_one]

    print('Tossed the coin and result is .. {toss}')

    if toss == guess:
      correct_guesses += 1

    total_guesses += 1

    print('---')

--- |
  Let's break this down a little bit. This small application is composed of many different pieces of functionality.

  ### Application Setup
  To play a coin toss game, we need a coin. Since, we cannot have a physical coin in our program, we can do the next best thing, have a list `['H', 'T']` to hold the possible choices that a user can make.

  ```Python
  choices = ['H', 'T']
  ```

  ### Application State
  Pretty much all applications maintain some information about the current state of the program. Unsurprisingly, it's called `state` or `application state` or `program state`. In this application, the state is:

  ```Python
  correct_guesses = 0
  total_guesses = 0
  ```

  We also have a `choices` list but the choices never change. So, we don't count it as `state`. `toss` could also be considered part of `state` but we don't really keep it around after we have used it.

  ### Control
  There is a while loop that keeps the application running. And there is a condition that we use to break out of the loop when user is done with playing.

  ```Python
  while True:
    ...
    if guess not in choices:
      break
  ```

  ### Keeping User Informed
  We keep user informed about the current score. For a `todo` application, it would be the count of `todo` or the `todo` list itself.

  ```Python
  print(f'Number of guesses: {correct_guesses} out of {total_guesses}.')
  ```

  ### Taking Input
  We give user a choice and take the input:

  ```Python
  guess = input('Heads or Tails (H/T)? ')
  ```

  ### Process the input
  Finally, we process the input and update the application state.

  ```Python
  zero_or_one = random.randint(0, 1)
  toss = choices[zero_or_one]

  if toss == guess:
    correct_guesses += 1

  total_guesses += 1
  ```

---
type: testless-coding-question
id: 0560f1e7-ac1e-4030-a173-58d30e8f5db8
question: |
  Extend the coin toss game. When the game exits, the program would print `Better luck next time` if the `50%` or less guesses were wrong. Otherwise, it would print `Not bad`.
code: |
  # your code goes here. You can copy paste the sample code here.

---
type: testless-coding-question
id: a2fd067b-bfb2-4319-b461-e4e5421cde63
question: |
  Extend the coin toss game. Instead of printing the message `Number of right guesses: 0 out of 1.`, the message should be `Number right guesses: 0 out of 1 heads and 2 out of 2 tails.` Here is a sample interaction:

  ```
  Number of right guesses: 0 out of 0 heads and 0 out of 0 tails.
  Heads or Tails (H/T)? H
  Tossed the coin and result is .. T
  ---
  Number of right guesses: 0 out of 1 heads and 0 out of 0 tails.
  Heads or Tails (H/T)? H
  Tossed the coin and result is .. H
  ---
  Number of right guesses: 1 out of 2 heads and 0 out of 0 tails.
  Heads or Tails (H/T)?
  ```

  Note: you'll need to change the way you manage application state.
code: |
  # your code goes here

---
type: testless-coding-question
id: ccf3f0bc-40f6-44d2-903e-e6c078af79ab
question: |
  Extend the coin toss game. Instead of offering 2 choices (`H/T`), offer 3 choices (`H/T/S`) where `S` stands for coin standing (it didn't fall on heads or tails side; just remained standing; yes, that can happen). Session looks like this:

  ```
  Number of right guesses: 0 out of 0.
  Heads or Tails (H/T/S)? H
  Tossed the coin and result is .. S
  ---
  Number of right guesses: 0 out of 1.
  Heads or Tails (H/T/S)? H
  Tossed the coin and result is .. H
  ---
  Number of right guesses: 0 out of 1.
  Heads or Tails (H/T/S)?
  ```
code: |
  # your code goes here
