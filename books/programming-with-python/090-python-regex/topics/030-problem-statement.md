title: Problem Statement
--- |

  Continuing from the previous section, here is the sample information you received from the students of your school:

  ```
  Google
  Facebook
  Instagram
  WattPad
  google.com
  facebook.com
  wattpad.com
  www.google.com
  www.facebook.com
  www.wattpad.com
  https://www.wattpad.com/tags/children
  https://www.facebook.com/home
  https://www.instagram.com
  ```

  Even though there is quite a variety in the way information is represented, there is a pattern here. You intuitively know that `wattpad`, `www.wattpad.com`, `https://www.wattpad.com/` and `https://www.wattpad.com/tags/children` mean the same thing in this context. They all mean that the student has singled out `wattpad` as the favorite site.

  This is where the problem is: how do you map all these variations of `wattpad` to just what it is (i.e. `wattpad`)? To your mind, the pattern is clear and you can easily see the mapping. However, if you were to write a program for this purpose, it would be a fairly involved task.

  This is where regular expresions shine. They give you a powerful language to describe the pattern (or the variations thereof).
