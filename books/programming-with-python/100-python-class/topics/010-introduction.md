title: Introduction
--- |
  Before we talk about what a `class` is and how to use it, let's delve a little into why a `class` kind of thing is needed. And for that, we'll go back to the basics and rebuild from there.

  In [anatomy of a Python program](/@python-program-anatomy), we started with this simple example:

---
type: live-code
id: 268ad8a5-dcce-40da-ae3d-cc934034959d
code: |
  4 + 5
--- |

  In this program, `4` and `5` are `values`. `+` is an `operator` that takes these two values, adds them up and produces the result `9`. So, within this program, the `expression` `4 + 5` becomes `9`.

  While all programming languages come with built-in `operators` (that usually take one or more values and produce another value), it would be very limiting if you had to use only the built-in `operators`. That's why, almost all programing languages also allow you to write `functions` that can `operate` on the values just as built-in `operators` do. So, if we wanted our own version of addition that takes a list of numbers and adds all of them together, we could write a `function` for that:

---
type: live-code
id: 0528282c-dbb6-4aa6-8e7e-3b21e65619fc
code: |
  def addition(numbers):
    total = 0
    for num in numbers:
      total += num

    return total

  addition([1, 2, 3])
--- |

  Of course, Python itself comes with a lot of built-in `functions` and then, we could write some of our own. In fact, we did write quite a few `functions` on our way to the topic of `classes`.

  While the `values` and the `operator` in these programs are visible, what's not apparent is the `type` of values. These values are of `type` `int`. The `+` `operator` also takes values of `type` `str` and concatenates them:
---
type: live-code
id: 7e570955-f627-4945-988b-72b6701b8d4b
code: |
 'hello' + ' ' + 'world'
--- |

  Every `value` is of a specific `type` (e.g. `int`, `str` etc). Python comes with built-in value `types` and then we can define our own custom `types`. Before we learn how we can create our own value `types`, let's look at a few that we have already dealt with (but not talked about).

  Consider the following code:
  ```Python
  numbers = [1, 2, 3, 4]
  basket = {'apple': 4, 'peaches': 2, 'pineapple': 3}
  ```

  Here, `numbers` is a value of `list` type and `basket` is a value of `dict` type. `tuple` and `set` are types too.

  We also worked with random numbers so far and it looked like the following:
  ```Python
  import random
  rand = random.randint(1, 100)
  ```

  Here, when we `import` something, we get a value of type `module`. In fact, all functions themselves are values of type `function`.

  More often than not, you would just work with the value `types` that are built into the Python language. However, from time to time, you would find it useful to define your own value `types`. Python `class` allows you to do that. In fact, even if you don't create your own value `types`, you would often end up using value `types` defined by others using Python `class`. So, it's important to add this to your list of tools.
