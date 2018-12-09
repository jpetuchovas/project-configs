# Configuration files for a Python project

## Environment setup

Download and install [Anaconda](https://www.anaconda.com/download/). Then create an environment using the command:

```bash
conda env create -f environment.yml
```

Activate the new environment using the command:

```bash
source activate python
```

### Automatic environment switching (optional)

If you want to switch to the created environment automatically every time you enter the project's directory, install [direnv](https://direnv.net/) (on Ubuntu, run the command `sudo apt-get install direnv`). For direnv to work properly it needs to be hooked into the shell. Therefore, update your shell's configuration file using [setup instructions](https://github.com/direnv/direnv#setup). Then follow these instructions to create a `.direnvrc` file: <https://github.com/direnv/direnv/wiki/Python#anaconda>. Finally, type `direnv allow .` in your project's directory.

## Usage

Run `pre-commit install` to install [pre-commit](https://pre-commit.com/) into your git hooks. pre-commit will now run on every commit.

## Code quality tools used

The following tools are used to check code quality:

- isort,
- Black,
- mypy,
- Bandit,
- flake8,
- pydocstyle.
