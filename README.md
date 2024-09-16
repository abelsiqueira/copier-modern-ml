# Copier Modern Machine Learning Template

[![Copier](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/copier-org/copier/master/img/badge/badge-grayscale-inverted-border-orange.json)](https://github.com/copier-org/copier)
[![CI](https://github.com/appleparan/copier-modern-ml/actions/workflows/ci.yml/badge.svg)](https://github.com/appleparan/copier-modern-ml/actions?query=workflow%3Aci)
[![docs](https://readthedocs.org/projects/copier-modern-ml/badge/?version=latest)](https://copier-modern-ml.readthedocs.io/en/latest/?badge=latest)

Personal [Copier](https://copier.readthedocs.io/en/stable/)
template with modern Python workflows

Inspired by [copier-uv](https://github.com/pawamoy/copier-uv) and [cookiecutter-data-science](https://github.com/drivendataorg/cookiecutter-data-science).

## Packaging Guide

* Check out [pyOpenSci Python Package Guide](https://www.pyopensci.org/python-package-guide/index.html)

## Features

* [rye](https://github.com/astral-sh/rye) for project and package management.
Included following tools.
  * [uv](https://github.com/astral-sh/uv) setup, with pre-defined `pyproject.toml`
  * Pre-configured tools for code formatting, quality analysis and testing:
  [ruff](https://github.com/charliermarsh/ruff),
  [mypy](https://github.com/python/mypy),
* Tests run with [pytest](https://github.com/pytest-dev/pytest) and plugins,
with [coverage](https://github.com/nedbat/coveragepy) support
* Documentation built with [mkdocs-material](https://github.com/squidfunk/mkdocs-material)
  and [mkdocstrings plugin](https://github.com/mkdocstrings/mkdocstrings))
* Support for GitHub workflows
* Auto-generated `CHANGELOG.md` from Git (conventional) commits.
[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/)

## How to use it

### Install dependencies

* Python 3.11+
* copier >= 9.3.1
* rye >= 0.38.0 (optional)

### Install copier

```bash
python -m pipx install copier copier_templates_extensions
```

### To start a new project, run

```bash
python -m copier copy --trust gh:appleparan/copier-modern-ml ~/path/to/your/project
```

then, install packages.

```bash
cd ~/path/to/your/project
rye sync
```

Finally, initialize git, then install `pre-commit` hooks.
(it takes some time at the first installation)

```bash
git init
rye run pre-commit install
git commit -m "First commit"
```

### The resulting directory structure

The directory structure of your new project will look something like this
(depending on the settings that you choose):

```plaintext
├── LICENSE            <- Open-source license if one is chosen
├── README.md          <- The top-level README for developers using this project.
├── mkdocs.yml         <- mkdocs-material configuration file.
├── pyproject.toml     <- Project configuration file with package metadata for
│                         {{ project_slug }} and configuration for tools like ruff
├── requirements.lock       <- The requirements lock file for reproducing the production environment, e.g. <!-- markdownlint-disable-line MD013 -->
│                              generated with `rye sync`
├── requirements-dev.lock   <- The requirements lock file for reproducing the development environment, e.g.<!-- markdownlint-disable-line MD013 -->
│                              generated with `rye sync`
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries <!-- markdownlint-disable-line MD013 -->
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g. <!-- markdownlint-disable-line MD013 -->
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
│
├── src/tests          <- Unit test files.
│
└── src/{{ project_slug }}   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes {{ project_slug }} a Python module
    │
    └── cli.py                  <- Default CLI program
```
