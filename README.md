# General purpose Python starter code with Jupyter and pre-commit
This repo has all of the dependencies that you need to run a basic Jupyter Notebook with some of the usual data processing tools. To set up from scratch do as follows.

## Get started
Update project name and description in `pyproject.toml`.

```bash
poetry install --with=dev && poetry shell
pre-commit install
```

## Python installation through Pyenv
Install Pyenv to manage installing multiple versions of Python in a clean way. A version manager is much cleaner than installing Python directly and will save you headaches solving version conflicts long term.

https://jordanthomasg.medium.com/python-development-on-macos-with-pyenv-2509c694a808

- Install the Python environment manager with the instructions above
  - Ensure you do the steps right for the particular `zsh` or `bash` shell you are using.
- (Optional) Install Python 2.7 and symlink it
- Set a Python global version e.g. Python 3.10.

## Environment management through Poetry
To keep your dependencies organized by project and prevent version conflicts we use environments and an environment manager. This environment manager will also help you install dependencies and clearly describe the package versions that you are using if you share the project with other developers.

Here's the Poetry installation docs. https://python-poetry.org/docs/. Simply execute the following command if in UNIX.

```{bash}
curl -sSL https://install.python-poetry.org | python3 -
```

Then do `poetry install` to install the environment in this repo and poetry shell to activate the environment on your shell. You should be able to run `ipython` or `jupyter notebook` now. You can add more dependencies with `poetry add <package>`, for more information, check out the docs.

## VS Code setup
A tricky part of the process is getting Jupyter Notebook to run on VS Code directly using this environment, but if you do you get the nice autocomplete and type checking features of VS Code when coding notebooks. Here's a rough guide of the steps to do this:
- Ensure that you installed the environment following the steps above.
- Install the relevant Python extensions. These would be the `Python` and `Jupyter` extensions.
- Run `poetry env info`. This will tell you the location of the Python interpreter, which will be the `Executable` attribute in the `Virtualenv` section in the output. Copy the interpreter path.
- `Cmd+Shift+P` Select Python Interpreter in VS Code. Select "Enter interpreter path". Then enter the path you got from the previous step. This makes VS Code recognize your Python kernel from now on on `.py` files and `.ipynb` files.
- Create a `notebook.ipynb` file. On the top right, select kernel. Then find your kernel named `basic-python-env` or whatever name you chose, and click on it. And you're set!
