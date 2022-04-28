---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.13.8
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

```{image} ../../logos/python_for_data_science.png
:alt: python programming for data science
:height: 100px
```
<hr>

+++

# Basic Data Types
<hr>

+++

A **value** is a piece of data that a computer program works with such as a number or text. There are different **types** of values: `42` is an integer and `"Hello!"` is a string. A **variable** is a name that refers to a value. In mathematics and statistics, we usually use variable names like $x$ and $y$. In Python, we can use any word as a variable name as long as it starts with a letter or an underscore. However, it should not be a [reserved word](https://docs.python.org/3.3/reference/lexical_analysis.html#keywords) in Python such as `for`, `while`, `class`, `lambda`, etc. as these words encode special functionality in Python that we don't want to overwrite!

It can be helpful to think of a variable as a box that holds some information (a single number, a vector, a string, etc). We use the **assignment operator** `=` to assign a value to a variable.

<!-- ![](img/chapter1/box.png)

Image modified from: [medium.com](https://www.google.com/url?sa=i&url=https%3A%2F%2Fmedium.com%2F%40stevenpcurtis.sc%2Fwhat-is-a-variable-3447ac1331b9&psig=AOvVaw3YbYfgb7XFOJ_sHP5eliob&ust=1595365663851000&source=images&cd=vfe&ved=0CA0QjhxqFwoTCMi8nrfe3OoCFQAAAAAdAAAAABAZ) -->

```{tip}
See the [Python 3 documentation](https://docs.python.org/3/library/stdtypes.html) for a summary of the standard built-in Python datatypes.
```

+++

## Common built-in Python data types

| English name          | Type name  | Type Category  | Description                                   | Example                                    |
| :-------------------- | :--------- | :------------- | :-------------------------------------------- | :----------------------------------------- |
| integer               | `int`      | Numeric Type   | positive/negative whole numbers               | `42`                                       |
| floating point number | `float`    | Numeric Type   | real number in decimal form                   | `3.14159`                                  |
| boolean               | `bool`     | Boolean Values | true or false                                 | `True`                                     |
| string                | `str`      | Sequence Type  | text                                          | `"I Can Has Cheezburger?"`                 |
| list                  | `list`     | Sequence Type  | a collection of objects - mutable & ordered   | `['Ali', 'Xinyi', 'Miriam']`               |
| tuple                 | `tuple`    | Sequence Type  | a collection of objects - immutable & ordered | `('Thursday', 6, 9, 2018)`                 |
| dictionary            | `dict`     | Mapping Type   | mapping of key-value pairs                    | `{'name':'DSCI', 'code':511, 'credits':2}` |
| none                  | `NoneType` | Null Object    | represents no value                           | `None`                                     |

+++

## Numeric data types

+++

There are three distinct numeric types: `integers`, `floating point numbers`, and `complex numbers` (not covered here). We can determine the type of an object in Python using `type()`. We can print the value of the object using `print()`.

```{code-cell} ipython3
x = 42
```

```{code-cell} ipython3
type(x)
```

```{code-cell} ipython3
print(x)
```

In Jupyter/IPython (an interactive version of Python), the last line of a cell will automatically be printed to screen so we don't actually need to explicitly call `print()`.

```{code-cell} ipython3
x  # Anything after the pound/hash symbol is a comment and will not be run
```

```{code-cell} ipython3
pi = 3.14159
pi
```

```{code-cell} ipython3
type(pi)
```

## Arithmetic Operators

Below is a table of the syntax for common arithmetic operations in Python:

| Operator |   Description    |
| :------: | :--------------: |
|   `+`    |     addition     |
|   `-`    |   subtraction    |
|   `*`    |  multiplication  |
|   `/`    |     division     |
|   `**`   |  exponentiation  |
|   `//`   | integer division / floor division |
|   `%`    |      modulo      |

Let's have a go at applying these operators to numeric types and observe the results.

```{code-cell} ipython3
1 + 2 + 3 + 4 + 5  # add
```

```{code-cell} ipython3
2 * 3.14159  # multiply
```

```{code-cell} ipython3
2 ** 10  # exponent
```

Division may produce a different `dtype` than expected, it will change `int` to `float`.

```{code-cell} ipython3
int_2 = 2
type(int_2)
```

```{code-cell} ipython3
int_2 / int_2  # divison
```

```{code-cell} ipython3
type(int_2 / int_2)
```

But the syntax `//` allows us to do "integer division" (aka "floor division") and retain the `int` data type, it always rounds down.

```{code-cell} ipython3
101 / 2
```

```{code-cell} ipython3
101 // 2  # "floor division" - always rounds down
```

We refer to this as "integer division" or "floor division" because it's like calling `int` on the result of a division, which rounds down to the nearest integer, or "floors" the result.

```{code-cell} ipython3
int(101 / 2)
```

The `%` "modulo" operator gives us the remainder after division.

```{code-cell} ipython3
100 % 2  # "100 mod 2", or the remainder when 100 is divided by 2
```

```{code-cell} ipython3
101 % 2  # "101 mod 2", or the remainder when 101 is divided by 2
```

```{code-cell} ipython3
100.5 % 2
```

## None

`NoneType` is its own type in Python. It only has one possible value, `None` - it represents an object with no value. We'll see it again in a later chapter.

```{code-cell} ipython3
x = None
```

```{code-cell} ipython3
print(x)
```

```{code-cell} ipython3
type(x)
```

## Strings

Text is stored as a data type called a `string`. We can think of a string as a sequence of characters.

```{tip}
Actually they are a sequence of Unicode code points. Here's a [great blog post](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/) on Unicode if you're interested.
```

We write strings as characters enclosed with either:
  - single quotes, e.g., `'Hello'`
  - double quotes, e.g., `"Goodbye"`

There's no difference between the two methods, but there are cases where having both is useful (more on that below)! We also have triple double quotes, which are typically used for function documentation (more on that in a later chapter), e.g., `"""This function adds two numbers"""`.

```{code-cell} ipython3
my_name = "Tomas Beuzen"
```

```{code-cell} ipython3
my_name
```

```{code-cell} ipython3
type(my_name)
```

```{code-cell} ipython3
course = 'DSCI 511'
```

```{code-cell} ipython3
course
```

```{code-cell} ipython3
type(course)
```

If the string contains a quotation or apostrophe, we can use a combination of single and double quotes to define the string.

```{code-cell} ipython3
sentence = "It's a rainy day."
```

```{code-cell} ipython3
sentence
```

```{code-cell} ipython3
type(sentence)
```

```{code-cell} ipython3
quote = 'Donald Knuth: "Premature optimization is the root of all evil."'
```

```{code-cell} ipython3
quote
```

## Boolean

The Boolean (`bool`) type has two values: `True` and `False`.

```{code-cell} ipython3
the_truth = True
```

```{code-cell} ipython3
the_truth
```

```{code-cell} ipython3
type(the_truth)
```

```{code-cell} ipython3
lies = False
```

```{code-cell} ipython3
lies
```

```{code-cell} ipython3
type(lies)
```

## Comparison Operators

We can compare objects using comparison operators, and we'll get back a Boolean result:

| Operator  | Description                          |
| :-------- | :----------------------------------- |
| `x == y ` | is `x` equal to `y`?                 |
| `x != y`  | is `x` not equal to `y`?             |
| `x > y`   | is `x` greater than `y`?             |
| `x >= y`  | is `x` greater than or equal to `y`? |
| `x < y`   | is `x` less than `y`?                |
| `x <= y`  | is `x` less than or equal to `y`?    |
| `x is y`  | is `x` the same object as `y`?       |

```{code-cell} ipython3
2 < 3
```

```{code-cell} ipython3
"Deep learning" == "Solve all the world's problems"
```

```{code-cell} ipython3
2 != "2"
```

```{code-cell} ipython3
2 is 2
```

```{code-cell} ipython3
2 == 2.0
```

## Boolean Operators

We also have so-called "boolean operators" which also evaluates to either `True` or `False`:

| Operator | Description |
| :---: | :--- |
|`x and y`| are `x` and `y` both True? |
|`x or y` | is at least one of `x` and `y` True? |
| `not x` | is `x` False? |

```{code-cell} ipython3
True and True
```

```{code-cell} ipython3
True and False
```

```{code-cell} ipython3
True or False
```

```{code-cell} ipython3
False or False
```

```{code-cell} ipython3
("Python 2" != "Python 3") and (2 <= 3)
```

```{code-cell} ipython3
True
```

```{code-cell} ipython3
not True
```

```{code-cell} ipython3
not not True
```

```{note}
Python also has [bitwise operators](https://wiki.python.org/moin/BitwiseOperators) like `&` and `|`. Bitwise operators literally compare the bits of two integers. That's beyond the scope of this course but I've included a code snippet below to show you them in action.
```

```{code-cell} ipython3
print(f"Bit representation of the number 5: {5:0b}")
print(f"Bit representation of the number 4: {4:0b}")
print(f"                                    ↓↓↓")
print(f"                                    {5 & 4:0b}")
print(f"                                     ↓ ")
print(f"                                     {5 & 4}")
```

## Casting

Sometimes we need to explicitly **cast** a value from one type to another. We can do this using functions like `str()`, `int()`, and `float()`. Python tries to do the conversion, or throws an error if it can't.

```{code-cell} ipython3
x = 5.0
type(x)
```

```{code-cell} ipython3
x = int(5.0)
x
```

```{code-cell} ipython3
type(x)
```

```{code-cell} ipython3
x = str(5.0)
x
```

```{code-cell} ipython3
type(x)
```

```{code-cell} ipython3
str(5.0) == 5.0
```

```{code-cell} ipython3
int(5.3)
```

```{code-cell} ipython3
:tags: [raises-exception]

float("hello")
```
