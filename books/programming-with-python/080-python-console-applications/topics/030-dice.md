title: Betting on Dice
---
type: testless-coding-question
id: aecc0709-cac6-4730-88e9-b75dc2cad7c4
question: |
  The goal is to build a simple game of dice. In the beginning of game, user has $10 for placing bets. The game asks the user to place a bet on a number between 1 to 6. Once the bet is placed, the dice is thrown. If the user wins the bet, user gets $5. However, if the user loses, $1 are taken out from user's balance. If the user's balance reaches less than $1, the game gets over with the message `Better luck next time`. Here is how the game starts

  ```
  Current Balance: $10
  What number do you place your bets on (1-6)?
  ```

  The game proceeds as follows:
  ```
  Current Balance: $10
  What number do you place your bets on (1-6)? 4
  Throwing the dice and the number is ... 3. You lost $1.
  ---
  Current Balance: $9
  What number do you place your bets on (1-6)? 2
  Throwing the dice and the number is ... 2. You won $5.
  ---
  Current Balance: $14
  What number do you place your bets on (1-6)?
  ```

code: |
  # your code goes here
