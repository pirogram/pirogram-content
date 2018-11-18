title: Creating Strings
--- |
  Strings can be created using single quote (`'`) or double quote (`"`) letters.

---
type: live-code
id: a165141e-2595-4784-b947-4c2b09e868ea
code: |
  s = 'string in single quote'
  s
---
type: live-code
id: dc8e2555-9f12-4424-8cce-a878a29fcc1c
code: |
  s = "string in double quote"
  s
--- |
  The single/double quote character within the string may need to be escaped with `\` character.

---
type: live-code
id: d9a12ad8-d2e1-4a89-aa4c-dbc9dd5802c5
code: |
  s = 'single quote can have " character'
  s
---
type: live-code
id: 06b8114a-cf02-4d32-81b1-abfb9b6667c4
code: |
  s = "double quote can have ' character"
  s
---
type: live-code
id: acbe891a-db60-4f27-a1ea-692b6024b26d
code: |
  s = 'single quote needs \' to be escaped'
  s
---
type: live-code
id: a294b694-3fb2-46fa-bae5-5e696835c694
code: |
  s = "double quote needs \" to be escaped"
  s

--- |
  Multi-line strings can be created using triple quote (`'` or `"`) characters.

---
type: live-code
id: efcdf7c8-c0d2-4e9f-8c82-573ddf58284e
code: |
  s = '''1st line.
  2nd line.'''

  s
---
type: live-code
id: 3cbad0c5-8f93-4f42-8c8b-2f49d10bdcff
code: |
  s = """1st line.
  2nd line."""

  s
