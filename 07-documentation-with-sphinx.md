---
title: Building Documentation with Sphinx
teaching: 0
exercises: 0
---

Sphinx is a tool for building documentation.

::::::::::::::::::::::::::::::::::::::: objectives

- Build a documentation website with sphinx
- Add overview documentation
- Distribute a sphinx documentation site

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How can I make my documentation more accessible

::::::::::::::::::::::::::::::::::::::::::::::::::

## What does sphinx produce?

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

In a group, have each member open one of the following packages' documentation

- [pytest](https://docs.pytest.org/en/latest/)
- [seaborn](https://seaborn.pydata.org/)
- [numpy](https://docs.scipy.org/doc/numpy/reference/)
- [scipy-cookbook](https://scipy-cookbook.readthedocs.io/)
- [scikit-learn](https://scikit-learn.org/stable/)

Discuss what the common components are, what is helpful about these
documentation sites, how they address the general concepts on documentation,
how they're similar and how they're different.

:::::::::::::::  solution

## Solution

these all use sphinx to generate them?



:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

## Sphinx quickstart

Install Sphinx if you haven't done so already:

```bash
pip install sphinx
```

Move into the directory that is to store your documentation:

```bash
cd docs
```

Start the interactive Sphinx quickstart wizard, which creates a Sphinx config file, `conf.py`, using your preferences.

```bash
sphinx-quickstart
```

Suggested responses to the wizard's questions:

- *Separate source and build directories?* -> yes
- *Project name* -> sensible to re-use the package name
- *Author name(s)* -> list of authors
- *Project release* -> sensible to re-use the package version specified in `setup.py` (see lesson 3) e.g. '0.1'
- Project language -> `en`, but you may want to target other languages as well/instead.

This will create:

- `docs/source/conf.py` -> Sphinx configuration file
- `docs/source/index.rst` -> Sphinx main index page, which like almost all Sphinx content, is written in reStructured Text (like Markdown)
- `docs/Makefile` -> for performing various tasks on Linux/macOS e.g. building HTML or a PDF
- `docs/make.bat` -> for performing those tasks on Windows

You should now be able to build and serve this basic documentation site using:

```bash
make html
python3 -m http.server -d build/html
```

When you browse to the URL shown in the output of the second command
you can see your HTML documentation site but it's looking fairly bare!
Let's learn a little more about reStructuredText then start adding some content to our documentation site.

## Adding literal documentation

FIXME: RST overview

FIXME: adding pages

## API Documentation

Add an api line to the `index.rst` so that it has a link to it.

The create an API.rst file:

```bash
API documentation
==================


```



:::::::::::::::::::::::::::::::::::::::: keypoints

- Building documentation into a website is a common way of distributing it
- Sphinx will auto build a website from plain text files and your docstrings

::::::::::::::::::::::::::::::::::::::::::::::::::


