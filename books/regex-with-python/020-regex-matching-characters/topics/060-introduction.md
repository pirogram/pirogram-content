title: Introduction
--- |

  In this section, we'll solve problems that revolve around presence or absence of certain characters in the text. For most of the problems, we'll use Hollywood movie names as the dataset where we do our pattern matching. It looks like the following:

  ```
  Abandoned
  Abbott and Costello Meet the Killer
  Abominable Dr. Phibes
  Abominable Snowman
  Above the Street
  Absent-Minded Professor
  Abyss
  ...
  Zoom
  Zoot Suit
  Zorba the Greek
  Zorn's Lemma
  Zorro
  Zotz!
  Zouzou
  Zozo
  ```

  Here are the kind of problems we'll solve around the movie names:

  * Finding movies that belong to a specific franchise (e.g. `Star Wars`).
  * Finding movies from multiple franchise (e.g. all movies from `Star Wars` as well as `Star Trek`).
  * Skipping movies from a specific franchise (e.g. all movies other than `Superman`). Or even all `Super` movies that are not `Superman`.
  * Finding movies that use a year in their name (e.g. `2001: A Space Odyssey`).
  * Finding movies with at least one five letter word (e.g. `Superman` is ok but `Cat and Dog` is not).
