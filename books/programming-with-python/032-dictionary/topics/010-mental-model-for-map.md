title: Mental Model for Map
--- |
  While `list` is a very useful data structure and regardless of the information you have, you can always find a way to organize it in the form of a list, there are times when using a `list` is very cumbersome. You want alternative ways of organizing the information. `Map` is one of those ways. In fact, one can argue that it is as important as list is. Let's look at a few examples where organizing information as a `Map` is useful.

  At Hogwarts, Dumbledore decided to measure the height of all students. He made the following observations:

  | Student | Height (cm) |
  | - | - |
  | Harry | 90 |
  | Hermione | 85 |
  | Ron | 92 |
  | Malfoy | 91 |

  Here, we map a student's name to his/her height. `Map` is a very useful abstraction and it can be applied in various situations. For example, the following maps a book to its author:

  | Book | Author |
  | - | - |
  | Harry Potter and the Goblet of Fire | J K Rowling |
  | Lord of the Rings | J R R Tolkien |
  | A Song of Fire and Ice | George R R Martin |

  The following maps a grocery item to its count:

  | Item | Count |
  | - | - |
  | potatoes | 20 |
  | tomatoes | 12 |
  | eggs | 18 |
  | apples | 6 |

  We can go on and on but hopefully, you got the idea of a `Map`.

  A `Map` can be seen as a list of key-value pairs. Each `key` maps to a `value`. `'Harry'` maps to `90`. Or `'Lord of the Rings'` maps to `'J R R Tolkien'`. Or `'eggs'` maps to `18`.

  What kind of things you can do with a `Map`? First, you can check whether a key is present or not (e.g. do we have `oranges` among our grocery items?).

  We can also find the value that a key maps to. For example, we can find out Ron's height. Or we can find out the author of _Lord of the Rings_.

  We can also add more entries, remove entries or update existing entries in the `Map`.
