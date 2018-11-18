title: Hangman
--- |
  We'll now write the famous Hangman game. We'll start with something simple and build upon that. You can use the following sample as question/answer set in your game. You can also come with your own question/answer set:

  ```
  Q: This city has Taj Mahal.
  A: Agra

  Q: This city has Golden Gate Bridge.
  A: San Francisco

  Q: This city has a very tall tower.
  A: Paris
  ```

---
type: testless-coding-question
id: f37feabf-1836-4499-9228-f064a0e901ce
question: |
  In our simplest version of Hangman, the program will randomly ask user a question. The user must guess the complete city name. If the user guesses correctly within 4 tries, the program will ask another question. Otherwise, the program would exit.

  Some more things to remember:
  * The user must not be shown a question that has already been shown.
  * If the user has answered all questions, the program would just exit.
  * The user can enter city name in UPPER, lower or Mixed case.

  Here is how the game starts:
  ```
  Q: This city has Golden Gate Bridge.
  A:
  ```

  And this is how it proceeds:
  ```
  Q: This city has Golden Gate Bridge.
  A: delhi
  Nope! Try again.
  A: san francisco
  Good Job!
  ==== ** ===
  Q: This city has Taj Mahal.
  A:
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: 27d21473-21dc-43e1-bced-df30771ab587
question: |
  We'll now further develop our program and allow the user to guess city name one character at a time. Here is how the interaction would look:

  ```
  Q: This city has Taj Mahal.
  A: ____
  Your guess: a
  Good job!
  ---
  Q: This city has Taj Mahal.
  A: A__A
  Your guess: b
  Nope!
  ---
  Q: This city has Taj Mahal.
  A (wrong so far - B): A__A
  Your guess: D
  Nope!
  ---
  Q: This city has Taj Mahal.
  A (wrong so far - B, D): A__A
  Your guess:
  ```
code: |
  # your code goes here

---
type: testless-coding-question
id: 2af239e6-f229-44c9-a90f-46c2153fb0ac
question: |
  We'll now enhance the game further and truly draw a hanging person. You can create multiple versions of the following ascii art to use in your program:
  ```
   _________
  |        |
  |        0
  |       /|\
  |       / \
  |
  |
  ```

  The interaction looks like this now:

  ```
   _________
  |      
  |    
  |      
  |      
  |
  |
  Q: This city has Taj Mahal.
  A: ____
  Your guess: a
  Good job!

   _________
  |      
  |    
  |      
  |      
  |
  |
  Q: This city has Taj Mahal.
  A: A__A
  Your guess: b
  Nope!

   _________
  |        |
  |    
  |      
  |      
  |
  |
  Q: This city has Taj Mahal.
  A: A__A
  Your guess: D
  Nope!

   _________
  |        |
  |        0
  |      
  |      
  |
  |
  Q: This city has Taj Mahal.
  A: A__A
  Your guess:
  ```
code: |
  # your code goes here
