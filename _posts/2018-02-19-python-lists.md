---
layout: post
title: "A few words on Python lists"
date: 2018-02-19
---

By teaching coding to beginners, or even experienced programmers transitioning to
Python, I noticed there are certain learning milestones that are likely to cause some
raised eyebrows.
Working with the list data structure in Python (or, more specifically, the *list
object*) can be confusing as some aspects of it can be less intuitive.
Understanding what's going on under the hood should be sufficient to clear up the
confusion.

What might contribute to the confusion during learning is that, in many ways, the handling of strings
and lists is quite similar. For example, we access individual elements with `[]`,
there are numerous built-in methods/functions used with the dot notation for each type, `+`
will in both cases add things (i.e., `"a" + "a"`, `[1] + [1]`), functions like
`sorted` and `len` will work with both, etc.
However, there are also substantial differences, and one of them is the fact
that lists in Python are mutable, while strings (unlike in some other
programming languages) are not. 

## 1+1

Here is an example of two different operations that both add an element to
a list, yet, they do it in a very different manner.
Given a list `lst`:

`lst = [1]`

There are two (obvious) ways to end up with a list `lst` that contains `[1, 1]`.
By using the built-in function `append`:

```python
lst.append(1)
```

or by concatenating `[1]` to the `lst`:

```python
lst = lst + [1]
```

While both approaches yield `lst = [1, 1]`, in the first case we used a built-in
function that mutated the list and returned `None`. In the second case, we
added `[1]` to the list and assigned the result to a new list which we also
called `lst` (again, this syntax might be familiar from the handling of
strings).

Although this might not seem as too big of a deal at first, let's explore what
happens in slightly more complex scenarios.

## Effects of mutation

Let us consider calling functions `add_sugar1` and `add_sugar2` with the list
`ingredients` as the argument in both cases:

```python
def add_sugar1(x):
    x.append('sugar')

def add_sugar2(x):
    x = x + ['more sugar']


ingredients = ['flour']
add_sugar1(ingredients)
add_sugar2(ingredients)
```

In both functions, when we pass `ingredients` as a function argument, the
parameter `x` will be a reference to the original list.
In the first case, `add_sugar1` uses that reference to modify/mutate the list.
Thus, the change to the list `ingredients` will persist even after we return
from the function. In the second case, a new list `x` is created, but changes
remain local to the function, and are not affecting the original list.

Here's another example that clarifies what is going on:
```python
x = [1, 2]
y = x

y.append(3)
x.append(4)
```

The assignment `y = x` did not actually copy the list, but it merely created
another variable used as a reference to the list `x`. That is why appending
anything to `y` also had the effect of changing `x` (and vice versa). 
If that code was just slightly different, i.e., instead of `y = x` we had `y
= x + []`, the results would have been different.
To create a copy of a list and not just the reference, we can do `y = x[:]`, or, less
obscure, `y = list(x)`.

