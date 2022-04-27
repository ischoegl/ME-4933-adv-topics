# ME-4933-adv-topics

## Installation

### Conda

Tests use a configured conda environment `jbook`

```
$ conda env create -f environment.yml
[...]

$ conda activate jbook
```

Update existing environment:

```
$ conda env update -f environment.yml --prune
```

### Compile the Jupyter Book

Build the book as

```
$ jupyter-book build .
```

## Notebooks with MyST Markdown

### Convert Jupyter Notebook to MyST

```
$ jupytext notebook.ipynb --to myst
```

### Quickly add YAML metadata for MyST Notebooks

```
$ jupyter-book myst init path/to/markdownfile.md
```
