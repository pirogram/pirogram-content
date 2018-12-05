title: Organize Map as List
--- |
  Let's look at the map of grocery items and their counts:

  | Item | Count |
  | - | - |
  | potatoes | 20 |
  | tomatoes | 12 |
  | eggs | 18 |
  | apples | 6 |

  This is _map-like_ information. The question is: how do you organize this information as a list? It does look a little _listy_ but there are nuances that we would need to deal with.

  One approach is to lay it out linearly with item name and the count alternating. For example, you could say:

---
type: live-code
id: e1a0d6c9-7603-4609-9df5-28c8a8d0e203
code: |
  grocery_items = ['potatoes', 20, 'tomatoes', 12, 'eggs', 18, 'apples', 6]

--- |
  In this approach, if we wanted to check how many eggs we need to buy, we could first locate the index of `eggs` within the list and retrieve the list item right after `eggs`. For example:

---
type: live-code
id: 2fecdae0-a5fc-47aa-a3c3-d21c712c4d2a
code: |
  grocery_items = ['potatoes', 20, 'tomatoes', 12, 'eggs', 18, 'apples', 6]

  eggs_index = grocery_items.index('eggs')
  eggs_count = grocery_items[eggs_index + 1]

  print('Eggs to buy:', eggs_count)

--- |
  If we wanted to add `8 oranges` to our grocery list, this is how we could do it:

---
type: live-code
id: eae9e476-9aa4-4809-9c56-3cde062e7bfc
code: |
  grocery_items = ['potatoes', 20, 'tomatoes', 12, 'eggs', 18, 'apples', 6]

  grocery_items.append('oranges')
  grocery_items.append(8)

  print(grocery_items)

--- |

  If we wanted to remove `tomatoes` from the grocery list, it would be a little twisted. We need to remove not only the `tomatoes` entry but also count of `tomatoes`. Here is how the code for same look like:

---
type: live-code
id: 9b446464-042b-4a55-bcd2-048a3dc8babe
code: |
  grocery_items = ['potatoes', 20, 'tomatoes', 12, 'eggs', 18, 'apples', 6]

  tomatoes_index = grocery_items.index('tomatoes')
  grocery_items.pop(tomatoes_index + 1)   # remove tomato count
  grocery_items.pop(tomatoes_index)       # remove tomatoes

  print(grocery_items)
--- |

  While this was possible, it felt twisted. It's like fitting the square pegs in round holes. Let's look at an alternate way to organize map-like information in a list.

  ## Alternate Approach
  We can also take the approach of storing grocery items and their respective counts in two separate lists. For example:

---
type: live-code
id: 1b3fe730-48f1-45d6-b42b-062a2984c138
code: |
  items = ['potatoes', 'tomatoes', 'eggs', 'apples']
  counts = [20, 12, 18, 6]

--- |

  In this example, we put all the grocery items in one list and all the counts in another list. We just make sure that items and their counts are organized in the same order. For example, in the list `items`, `potatoes` is the first item (i.e. the item at index `0`). The count for `potatoes` is `20` and it is first in the `counts` list. Similarly, `eggs` is 3rd in `items` list and its count is 3rd in the `counts` list.

  Now, if we want to find out how many `eggs` we need to buy, we can approach it as follows:

---
type: live-code
id: 1b0d0334-681f-4fb4-bd29-9b4e1004f718
code: |
  items = ['potatoes', 'tomatoes', 'eggs', 'apples']
  counts = [20, 12, 18, 6]

  eggs_index = items.index('eggs')
  eggs_count = counts[eggs_index]

  print(eggs_count)
--- |
  If we want to add `8 oranges` to the list, we'll add `oranges` to items and `8` to counts list.

---
type: live-code
id: d44beedb-72bd-4a3b-b0e4-0d66368bbd63
code: |
  items = ['potatoes', 'tomatoes', 'eggs', 'apples']
  counts = [20, 12, 18, 6]

  items.append('oranges')
  counts.append(8)

  print(items)
  print(counts)

--- |
  If we want to remove `tomatoes`, we need to remove it from both the lists:

---
type: live-code
id: 1e0b0067-11e4-4056-ace7-e6ea988a7883
code: |
  items = ['potatoes', 'tomatoes', 'eggs', 'apples']
  counts = [20, 12, 18, 6]

  tomatoes_index = items.index('tomatoes')
  items.pop(tomatoes_index)
  counts.pop(tomatoes_index)

  print(items)
  print(counts)
--- |
  So, there are multiple ways to model _map-like_ information in a list. However, we should be able to do better. `dict` allows us to do better...
