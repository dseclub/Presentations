# Python virtual environments and dependency management

## Plan

1. [Why](#why)
2. [What](#what)
3. [Why each](#why-each)
4. [Links](#links)
5. [Notes](#notes)
6. [About me](#about)

## Why

To prevent your project from:

- crushing your computer
- crushing your other project
- suddenly breaking in production

To make your project easy to:
- secure
- maintain
- deploy
- share

## What

Not strictly related, 
- but [pyenv](https://github.com/pyenv/pyenv) is good to have.


Various env and maintenance management solutions:
- [hatch](https://hatch.pypa.io/latest/) - use this one
- [venv](https://docs.python.org/3/library/venv.html) - stdard, start here
- [conda](https://anaconda.org/anaconda/conda) - hack away - fastest way to get started
- [poetry](https://python-poetry.org/)
- [pdm](https://pdm-project.org/en/latest/)
- [pipenv](https://pipenv.pypa.io/en/latest/)
- [virtualenv](https://virtualenv.pypa.io/en/latest/)
- [setuptools](https://pypi.org/project/setuptools/)

> Separately, I recommend using [pyenv](https://github.com/pyenv/pyenv)

## Why each

### hatch

It is the most modern solution, authorized by PyPA (python's body to authorize solutions). 
It helps to manage the whole python project assets, including bundling, packaging, publishing, testing etc. I will use it in my next project.

Example: 

```sh
hatch new "Hatch Demo"
```

```
hatch-demo
├── src
│   └── hatch_demo
│       ├── __about__.py
│       └── __init__.py
├── tests
│   └── __init__.py
├── LICENSE.txt
├── README.md
└── pyproject.toml
```

Example from https://hatch.pypa.io/latest/intro/#setup

### venv

Easy, it's there, comes with python! (unless you use python from before 2012 or v.<3.3)

```sh
cd my-project
python -m venv .venv
source .venv/bin/activate # on mac/linux
.venv/bin/Scripts/activate # on windows
```

### conda

Data-science batteries included. Long-term that's a drawback. Generally better to only install what you need

Conda create package for you, manage libraries (yaml file). It uses own channels instead of PyPI. Will install not only python, but also other-language libraries.

### poetry

Creates a package structure for you, manages the environement and dependencies.
Separates dev & prod libraries. Uses pyproject.toml & poetry.lock

### pdm

Very similar to poetry, faster in resolving dependencies.

### pipenv

Similar to poetry but maybe simplier. Uses Pipfile and Pipfile.lock. Automatically nandles `.env` file. I like working with this for projects like websites or apis that will not become libraries.

### virtualenv

If you need to work with Python 2 or somehow still with python < 3.3. It is legacy and dominated virtual environment scene before python started bringing `venv` by default.

### setuptools

A traditional library for packaging your python code into library.

## Links

https://pypi.org/project/hatch/
https://packaging.python.org/en/latest/tutorials/packaging-projects/
https://www.pypa.io/en/latest/

What is the wheel format: 
https://peps.python.org/pep-0427/

## Notes:

- tox, nox - test your project w. multiple versions of python
- pew - if you use virtualenv, will help managing virtual envs

## About Krzysztof Lechowski

- Co-host, [Data Science and Engineering Club](https://www.meetup.com/data-science-and-engineering-club/)
- Director, [Archmedian Ltd](https://archmedian.com)
- Sr Data Engineer, Hertz
- coder, analyst
