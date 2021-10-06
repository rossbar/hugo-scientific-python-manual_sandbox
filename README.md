# Publishing executable docs w/ hugo

Test a hugo+pandoc+jupytext workflow for generating scientific Python docs 

## Attempt 1: MyST notebook (markdown), execute with jupytext, convert with hugo

```
jupytext --from myst --to myst --execute notebooks/index.md \
         --update-metadata '{"title": "nb", "markup": "pandoc"}' \
         -o content/posts/nb.md
```

- Uses jupytext to execute notebook
- `--update-metadata` used to embed hugo-theme-specific info in yaml header
- stores output in `content/posts` where hugo looks for content

**Problem**
- `myst` markdown notebooks don't store output, so while the notebook may be
  *executed*, the output isn't embedded in the notebook for the hugo conversion
  step. **N.B.** - `--update` flag for `jupytext` has no effect: not storing output
  is part of the myst notebook format (I think).

## Attempt 2: MyST notebook (markdown), execute+convert to pandoc, convert with hugo

Similar to the above except replace `--to myst` with `--to pandoc` to get a
[pandoc-style Jupyter notebook](https://pandoc.org/MANUAL.html#jupyter-notebooks).

**Problems**
- Similar to above: output is not stored in pandoc-style notebook format even
  after execution.
- hugo pandoc engine doesn't appear to recognize the pandoc-style notebook format
