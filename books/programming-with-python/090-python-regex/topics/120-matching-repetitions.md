title: Matching Repetitions
--- |
  So far, we have looked at specifying *which characters* are allowed and which ones are not allowed in the pattern. Now, we'll look at specifying *how many* are allowed.

  Let's revisit the problem of matching movie names with at least 6 letters. We know that `1984` is not a match and `Superman` is a match. The pattern we wrote was `......`. Basically, a `.` (which matches all characters) repeated 6 times.

  Regex has mechanisms to say precisely how many times a match should occur. This is what we'll study in this section.
