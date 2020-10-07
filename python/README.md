# [DEPRECATED] Configuration files for a Python project

No longer maintained.

## Environment setup

Download and install [Anaconda](https://www.anaconda.com/download/). Then create an environment called `python-project` using the command:

```bash
conda env create -f environment.yml
```

Activate the new environment using the command:

```bash
source activate python-project
```

### Automatic environment switching (optional)

If you want to switch to the created environment automatically every time you enter the project's directory, install [direnv](https://direnv.net/) (if you are using Ubuntu, run the command `sudo apt-get install direnv`).

For direnv to work properly it needs to be hooked into the shell. Therefore, update your shell's configuration file using [setup instructions](https://github.com/direnv/direnv#setup). If you want your shell's prompt to indicate which environment you are using, also add the following at the end of your shell's configuration file (if you are using bash, the configuration file is `~/.bashrc`):

```bash
show_virtual_environment() {
  if [ -n "$CONDA_DEFAULT_ENV" ]; then
    echo "($(basename $CONDA_DEFAULT_ENV)) "
  fi
}

export -f show_virtual_environment
PS1='$(show_virtual_environment)'$PS1
```

Then follow these instructions to create a `.direnvrc` file: <https://github.com/direnv/direnv/wiki/Python#anaconda> (replace `local ANACONDA_HOME="${HOME}/miniconda3/"` with `local ANACONDA_HOME="${HOME}/anaconda3/"` if your are using Anaconda, or leave it untouched if you are using Miniconda).

Finally, type `direnv allow` in your project's directory (you may need to restart the terminal for the changes to take effect).

## Usage

Run `pre-commit install` to install [pre-commit](https://pre-commit.com/) into your git hooks. pre-commit will now run on every commit.

## Code quality tools used

The following tools are used to ensure code quality:

- isort,
- Black,
- mypy,
- Bandit,
- flake8,
- pydocstyle.
