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

```{image} ../logos/matplotlib.svg
:alt: matplotlib
:height: 100px
```
<hr>

+++

# `matplotlib`
<hr>

+++

[Matplotlib](https://matplotlib.org) is a comprehensive library for creating static, animated, and interactive visualizations in Python. Although the core functions in Matplotlib are for 2-D data plots, there are extensions available that allow plotting in three dimensions with the [mplot3d](https://matplotlib.org/stable/api/toolkits/mplot3d.html) package and various [third-party packages](https://matplotlib.org/mpl-third-party/).

```{tip}
Here are some more resources on Matplotlib:

* [Matplotlib Users Guide](https://matplotlib.org/stable/users)
* [Matplotlib Tutorials](https://matplotlib.org/stable/tutorials)
* [Matplotlib Documentation](https://matplotlib.org/stable)
* [Scientific Visualization: Python + Matplotlib](https://github.com/rougier/scientific-visualization-book)
```

+++

## Brief Introduction
<hr>

Load necessary modules

```{code-cell} ipython3
import numpy as np # math
import matplotlib.pylab as plt # plotting
```

Create an array of points

```{code-cell} ipython3
x = np.linspace(-2,2,201)
```

### Simple Plot

Plot functions into one common figure

```{code-cell} ipython3
plt.plot(x, np.sin(np.pi*x), label='some function')
plt.plot(x, np.cos(np.pi*x), label='another function')
ax = plt.gca()
ax.set_title('some title')
ax.set_xlabel('x axis title')
ax.set_ylabel('y axis title')
ax.legend()
```

### Subfigures

```{code-cell} ipython3
fig, ax = plt.subplots(1,2,sharey=True)
ax[0].plot(x,np.sin(np.pi*x),label='some function')
ax[1].plot(x,np.cos(np.pi*x),label='another function')
ax[0].set_title('some title')
ax[1].set_title('another title')
ax[0].set_ylabel('y axis title')
for axx in ax:
    axx.legend()
    axx.set_xlabel('x axis title')
```

## Next Steps
<hr>

Review [Matplotlib Basic Usage](https://matplotlib.org/stable/tutorials/introductory/usage.html) example.
