# Python project setup

Basic Python project as an example for how to setup a project.

## setup

### basic

- create a directory for the library in `src`
- create empty `__init__.py` ("required to import the directory as a package, and should be empty.")
- lint: ignore docstring issues (doc strings can be verbose)

### virtual environment

```
python3 -m venv .env
source .env/bin/activate
```

### create PyPi/pip-installable package

#### setuptools and pyproject.toml

- create `src/setup.py`
- create `pyproject.toml`
- upgrade `build`: `pip install --upgrade build`
- build: `python3 -m build`

Create project metadata in `pyproject.toml` (minimmal `setup.py`)

#### test locally

`pip install ./dist/simple_project_pretorh-0.0.3.tar.gz` and start `python`:

```python
from simple_project_pretorh import hello
hello.add_one(1)
hello.say_hello('test')
```

#### uploading to test.pypi.org

```
pip install twine
twine upload --repository-url https://test.pypi.org/legacy/ dist/*
```

## links

- https://packaging.python.org/en/latest/tutorials/packaging-projects/
- [high level/minimal](https://stackoverflow.com/a/47298178)
- [pyproject_config.toml with setuptools](https://setuptools.pypa.io/en/latest/userguide/pyproject_config.html)
