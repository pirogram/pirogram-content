title: Gibberish To Rescue
--- |

  To an untrained eye, regular expressions look like gibberish and that's how we'll treat them in this section. Once you are done with the entire material, they'll not be gibberish anymore. We'll get there...

  #### Revisiting the Problem

  We want to extract the website name (i.e. `wattpad`) from different ways in which it is given to us (i.e. `wattpad`, `www.wattpad.com`, `https://www.wattpad.com/` and `https://www.wattpad.com/tags/children`).

  #### The Solution

  The solution has two parts to it:

  * First, we define a pattern that would match all variations in which people mentioned the site name (i.e. `wattpad`, `www.wattpad.com`, `https://www.wattpad.com/` and `https://www.wattpad.com/tags/children`)
  * Next, we'll use the pattern to extract the actual site name (i.e. `wattpad`) from its variations.

  Here is the gibberish (aka regular expression) that describes the pattern we are looking for. Don't even try to understand it for now. Just take it as it is.

  ```Python
  REGEX_GIBBERISH = r"(https?://)?(www\.)?(?P<site>\w+)(\.com)?"
  ```

  Here is the code that makes use of `REGEX_GIBBERISH`, applies it to the site name as entered by the students and gives us the bare bone site name as we want to see.

  ```Python
  # Import the regular expression module
  import re

  # Define the regex pattern
  REGEX_GIBBERISH = r"(https?://)?(www\.)?(?P<site>\w+)(\.com)?"

  # Apply the pattern to whatever site name was entered by students
  # and get the barebone site name.
  re.search(REGEX_GIBBERISH, "...site name...").group("site")
  ```

  Let's see this code in action now.

  ```Python
  >>> import re
  >>> REGEX_GIBBERISH = r"(https?://)?(www\.)?(?P<site>\w+)(\.com)?"
  >>>
  >>> re.search(REGEX_GIBBERISH, "wattpad").group("site")
  'wattpad'
  >>> re.search(REGEX_GIBBERISH, "wattpad.com").group("site")
  'wattpad'
  >>> re.search(REGEX_GIBBERISH, "www.wattpad.com").group("site")
  'wattpad'
  >>> re.search(REGEX_GIBBERISH, "http://www.wattpad.com").group("site")
  'wattpad'
  >>> re.search(REGEX_GIBBERISH, "https://www.wattpad.com").group("site")
  'wattpad'
  >>> re.search(REGEX_GIBBERISH, "https://www.wattpad.com/tags/children").group("site")
  'wattpad'
  >>>
  ```

  Fascinating. Isn't it?
