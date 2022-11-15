---
title: Managing Python Environments with VirtualEnv
teaching: 0
exercises: 0
---

## Environments and Package managers

::::::::::::::::::::::::::::::::::::::: objectives

- Identify an environment, dependencies, and an environment manager
- Install an older version of python
- Use virtualenv to create an environment per project
- Store a projects' dependencies
- install dependencies for a project

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How can I make sure the whole team (or lab) gets the same results?
- How can I simplify setup and dependencies for people to use my code or reproduce my results?

::::::::::::::::::::::::::::::::::::::::::::::::::

An environment consists of a certain Python version and some packages. A virtual environment allows you to have multiple, independent versions of python on your system. Environments can also be saved so that you can install all of the packages and replicate the environment on a new system.

Why use one:

- to deliver code and keep it the same versions
- to use contribute to a package you also use
- to install on servers
- to share your environment with others

how to chose which of the main strategies to use: `virtualenv` and `pip` or `conda`

`conda` comes from Anaconda and does both package management and provides a virtual environment.

`pip` is the main python package installer

`virtualenv` creates environments and are `pip` install compatible.

Making your own packages pip installable requires fewer dependencies, so we'll focus on `virtualenv` and `pip` in this workshop

<!-- ## Dependencies

what are dependencies?

> ## Exercise
> FIXME -->

## Create an environment

Before we create an environment, let's see what happens when we import one of
our favorite packages.  In a python interpreter:

```python
import numpy
```

That should work, because we have the package installed on our system. If not,
use a package you know you have installed, or install numpy.

Next, we'll create an environment an environment from scratch.

```bash
virtualenv myenv
```

if python 3 isn't your default you might need to pass the version of python that you want installed:

```bash
virtualenv myenv -p python3.6
```

then we can activate the environment

```bash
source myenv/bin/activate
```

Now we see that the cli changes to show the environment name and we can further
test our environment with our favorite package from before.

```python
import numpy
```

Now, it won't work, but we can install it and a few other favorites.

```bash
pip install numpy
```

## save an environment

```bash
pip freeze > requirements.txt
```

## Deactivate an environment

When you're done with an environment, you exit it with deactivate.  Also note
that an environment only exists in the one terminal window. If you open a new
terminal, you'll be back to your default environment.

```bash
deactivate
```

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise

download a project, create a new environment and install from the
requirements file

Hint: use the pip man file to find options you can pass to `pip install`

:::::::::::::::  solution

## Solution

```bash
pip install -r requirements.txt
```

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::



:::::::::::::::::::::::::::::::::::::::: keypoints

- A python dependency is another, independent package that a given project uses and requires to be able to run
- An environment is
- An environment manager enables one step installing and documentation of dependencies, including versions
- Virtualenv is ...

::::::::::::::::::::::::::::::::::::::::::::::::::


