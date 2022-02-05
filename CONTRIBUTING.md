# Contribution Guidelines
These guidelines must be followed before any pull request will be accepted. If your not sure about something, just do your best.

## Basics
Libraries and repos in TrigonDev use `poetry` as a package manager. It's pretty straightforward:
 1. `pip install poetry` to install poetry.
 2. `poetry install` to install the repo/library for development.
 3. `poetry run ...` to run a command inside the virualenv created by poetry. You can also type `poetry shell` to enter that env, and then `exit` to exit it.

Some other useful commands:
 - `poetry add <name>`: Add a dependency.
 - `poetry add <name> --dev`: Add a development dependency (for example, `flake8` is a dev dep).
 - `poetry remove <name> [--dev]`: Remove a dependency.

More info can be found at [poetry's website](https://python-poetry.org).

## General Style
 - CI must pass. `nox` will be run automatically for new PRs, but it will be easier for you to run it yourself. Just run `nox` to run the pipeline.
 - Code should have static type hints (don't just use `Any` for everything). If a function or method returns `None` (either with `return None` or no return at all), that function should still be typed to return None (otherwise mypy will assume Any).
 - Avoid using `# pragma: no cover`, `# noqa`, and `# type: ignore` unless you have a very good reason for it.

## Naming
Functions, methods, classes, variables (constants and properties), and classvars that are meant for public use should have docstrings (use `google` style for functions & methods). Non-public API should start with `_` (`_some_function`).

If you edit a function/method/class that already has a docstring, make sure to update the docstring to match.
