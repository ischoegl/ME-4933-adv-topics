---
html_meta:
  "robots": "noindex"
---

![](../../logo.png)

+++

# Why Python?
<hr>

Some thoughts on [Matlab vs. Python](https://realpython.com/matlab-vs-python/)

+++

## Ease of Use
<hr>

A short and imprecise definition of differences between programming languages is (adapted from a
[stackoverflow answer](https://stackoverflow.com/questions/3265357/compiled-vs-interpreted-languages)):

* **Compiled language:** Entire program is translated to machine code at once, then the machine code is run by the CPU. Advantages are:

  * Faster performance by directly using the native code of the target machine
  * Opportunity to apply quite powerful optimizations during the compile stage

* **Interpreted language:** Program is read line-by-line and as soon as a line is read the machine instructions for that line are executed by the CPU. Advantages are:

  * Easier to implement (writing good compilers is very hard!!)
  * No need to run a compilation stage: can execute code directly "on the fly"
  * Can be more convenient for dynamic languages

* **Hybrid approaches:** At this point, few languages these days are purely compiled or purely interpreted, and are often a mix (see [blog post](https://orangejuiceliberationfront.com/the-difference-between-compiler-and-interpreter/)).

Python falls in the third category; while it is not compiled to machine code ahead of time, it is compiled to [bytecode](https://en.wikipedia.org/wiki/Bytecode) that is then executed by the Python virtual machine.

+++

## Ease of Installation
<hr>

Python can be downloaded from a number of different sources, called **distributions** (Example: Python downloaded from the [official Python website](https://www.python.org/)).

### Google Colab - No Configuration Needed

[Colab](https://colab.research.google.com/), or "Colaboratory", allows users to write and execute Python in a browser, without a need for configuration.

### Anaconda

[Anaconda](https://www.anaconda.com/products/distribution) is a Python distribution commonly used for math, science, engineering, and data science applications.

### Other Python Distributions

* [official Python](https://www.python.org/)
* [PyCharm](https://www.jetbrains.com/pycharm/)
* [Visual Studio](https://visualstudio.microsoft.com/vs/features/python/)

+++

## Great Community Support
<hr>

+++

## Alternatives
<hr>

* MATLAB
* C/C++
* Java
* Julia
* Rust
* R

+++
