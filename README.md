# python-venv-execution

A Zed agent skill that pins Python execution and formatting to a project's
own `.venv`, keeping the host environment out of the loop.

## Enforced

- Run Python as `.venv/bin/python`, never bare `python` or `python3`.
- Run Ruff via the venv interpreter: `.venv/bin/python -m ruff format .`,
  never a host-installed `ruff` on `PATH`.
- No installs or environment mutations; if Ruff is missing, report it.

## Install

Open the command palette (**Ctrl+Shift+P**, or **Cmd+Shift+P** on macOS), run
`agent: create skill from url`, and paste:

```
https://raw.githubusercontent.com/scr255/python-venv-execution/main/SKILL.md
```
