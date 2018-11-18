title: Matching Boundaries
--- |
  Let's say, we want to match the text which has the word `cat` in it. We could use the regex `cat`. This regex would match `cat is fat`, `the cat jumped over the wall` etc. But it would also match `he was herding the cattle` :(

  If we modify the regex to `cat\s`, we can avoid matching `he was herding the cattle`. But it would still match `this muscat is funny`.

  How about `\scat\s` as the regex? The problem is that it would not match `cat jumped` or `this is my cat.`.

  Regex has the ability to match boundaries of words & lines that would help us in this scenario. Let's see how...
