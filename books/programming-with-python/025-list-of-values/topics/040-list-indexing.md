title: List Indexing
--- |
  Now we come to a part that's very troublesome for new programmers i.e. list indexing. However, with some practice (and patience), we can easily master this concept.

  Since all items in a list are ordered, we can actually number them in a sequence. Let's look at the following list which represents the outcome of tossing a coin 8 times:

  ```python
  toss_outcomes = ['H', 'H', 'T', 'H', 'T', 'T', 'T', 'H']
  ```

  In this list, we can easily number the outcomes. We could say that 1st was Heads, 2nd was Heads, 3rd was Tails, 4th was Heads etc. Once we have numbered them, we could also frame various types of questions. For example, we could ask what was the outcome of 7th coin toss? Or was Heads the outcome of 6th coin toss? Or when was the first time we got a Tails?

  All lists are implicitly indexed with a sequence and we'll learn to answer all these questions with that index. But first a nuance. The sequence for list index starts from `0` instead of `1`. So, if we want to know the outcome of `1st` coin toss, we have to really look at the item at `0th` index. Similarly, if want the outcome for `7th` toss, we need to look at `6th` index.

  It's kind of weird in the beginning. In fact, I have been programming for 20 years and it still feels weird. But you get used to the weirdness after a while.

  So, how do we find answers to the fancy questions that we posed for coin toss? `toss_outcomes[6]` will tell us the outcome at `6th` index (which is same as 7th toss).

---
type: live-code
id: b69e8a08-5ed7-4008-8626-4b6409de98e5
code: |
  toss_outcomes = ['H', 'H', 'T', 'H', 'T', 'T', 'T', 'H']

  toss_outcomes[6]
--- |

  Was the 6th coin toss (i.e. index number 5) Heads?

---
type: live-code
id: 216bb54e-19f5-40e1-9d4d-b213148d3231
code: |
  toss_outcomes = ['H', 'H', 'T', 'H', 'T', 'T', 'T', 'H']

  if toss_outcomes[5] == 'H':
    print('It was heads')
  else:
    print('It was tails')
--- |

  When was the first time we got Tails?

---
type: live-code
id: ba2e8bc4-f713-4685-89d3-d97daa834fbd
code: |
  toss_outcomes = ['H', 'H', 'T', 'H', 'T', 'T', 'T', 'H']

  index = toss_outcomes.index('T')
  print('First Tails: index number - ', index, 'and toss number - ', index+1)

--- |

  One way to think about list indices is still in the form of symbol tables. Let's look at the following code:

  ```python
  heads = 'H'
  tails = 'T'
  outcomes = [heads, heads, tails, heads]
  ```

  The symbol table for this can be visualized as follows:

  <table class='ui celled table'>
    <thead>
      <th>Symbol</th>
      <th>(index)</th>
      <th>Value</th>
    </thead>
    <tbody>
      <tr>
        <td>heads</td><td></td>
        <td>'H'</td>
      </tr>
      <tr>
        <td>tails</td><td></td>
        <td>'T'</td>
      </tr>
      <tr>
        <td>outcomes</td>
        <td>0</td>
        <td>'H'</td>
      </tr>
      <tr>
        <td>outcomes</td>
        <td>1</td>
        <td>'H'</td>
      </tr>
      <tr>
        <td>outcomes</td>
        <td>2</td>
        <td>'T'</td>
      </tr>
      <tr>
        <td>outcomes</td>
        <td>3</td>
        <td>'H'</td>
      </tr>
    </tbody>
  </table>
