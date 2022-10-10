% my-project documentation master file, created by
% sphinx-quickstart on Fri Oct  7 22:08:01 2022.
% You can adapt this file completely to your liking, but it should at least
% contain the root `toctree` directive.

[![Version](https://img.shields.io/pypi/v/my-package-tomergabay)](https://pypi.org/project/my-package-tomergabay/)
![](https://img.shields.io/github/license/sTomerG/my-package)
![](https://img.shields.io/pypi/pyversions/my-package-tomergabay)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

# The template for a professional Python Package

In October 2022 I wrote [this](link) Medium article in which I explain step-by-step on how to create a professional Python Package. To make it extra easy for everyone I've also created [this](https://github.com/sTomerG/my-package) repository which can be used as a template.

## Contents

- A *src/* folder with example code.
- A *pyproject.toml* with all the necessary dependencies specified.
- A *tests/* folder with example tests, using pytest and Hypothesis.
- Pre-commit hooks for *Black*, isort and flake8.
- A workflow *test-package.yaml* which automates testing with Github Actions for different Python versions (optionally) on different Operating Systems, using caching to speed up the process.
- A *docs/* folder with a Sphinx project template for ReadTheDocs which can easily be auto-generated with one command, including automatic API documentation of all code in *src/*.

## Usage

To convert this package template to your own package please take the following steps:

1. Clone this repository: `git clone https://github.com/sTomerG/my-package.git`

2. Create a virtual environment using pyenv and pyenv-virtualenv or `python3 -m venv venv`

3. Activate the virtual environment using using pyenv or `source venv/bin/activate`

4. Upgrade pip and install poetry: `pip install --upgrade pip && pip install poetry`

5. Activate the poetry venv with `poetry shell` if you're using pyenv.
   
6. Change some fields of `[tool.poetry]` in *pyproject.toml*, e.g. the project name, in field `name` and `packages`

7. Change the name of the *my_package/* folder in *src/* to the new name of your package (use underscores instead of hyphens here).

8. Change the top fields in *docs/source/conf.py*, e.g. `project` to the same value as `name` in *pyproject.toml*. 

9. Reinstall the package with `poetry install`

10.  Change the `my_package` part in  `from my_package.calc import` to the name of the folder you chose in step 6 in *tests/test_calc/test_square.py* and in *docs/source/notebooks/usage.ipynb*.

11. Check if the tests are still running correctly with working with `poetry run pytest` 

12. Rebuild the docs with `poetry run sphinx-autobuild docs/source docs/build/html`

13. Edit in the top of the README the links

## Note

When you add dependencies with `poetry add`, make sure to also run `poetry export --with doc -f requirements.txt --output docs/rtd_requirements.txt` to update the requirements file for the ReadTheDocs.

```{toctree}
:caption: 'Contents:'
:maxdepth: 2

notebooks/usage
```

# Indices and tables

- {ref}`genindex`
- {ref}`modindex`
- {ref}`search`
