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

### setup tools

- create `src/setup.py`
- build source distribution: `python setup.py sdist`

### pyproject.toml

- create `pyproject.toml`
- upgrade `build`: `pip install --upgrade build`

move project metadata into `pyproject.toml` (minimmal `setup.py`)

### test locally

`pip install ./dist/simple_project_pretorh-0.0.2.tar.gz` and start `python`:

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
