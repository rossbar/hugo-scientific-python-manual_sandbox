---
jupytext:
  notebook_metadata_filter: all
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.13.0
kernelspec:
  display_name: Python 3
  language: python
  name: python3
language_info:
  codemirror_mode:
    name: ipython
    version: 3
  file_extension: .py
  mimetype: text/x-python
  name: python
  nbconvert_exporter: python
  pygments_lexer: ipython3
  version: 3.9.7
---

# Example notebook

Example notebook for testing a non-sphinx-based execution workflow for
executable content in a hugo site.

```{code-cell} ipython3
import numpy as np
import matplotlib.pyplot as plt

rng = np.random.default_rng()
static = rng.random((640, 480))
np.mean(static)
```

The above should include an output box showing the computed mean.

Now let's try a figure:

```{code-cell} ipython3
plt.imshow(static.T)
```
