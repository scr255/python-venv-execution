---
name: python-venv-execution
description: Enforces using the project's local virtual environment (.venv/bin/python) for Python execution and Ruff formatting, and forbids global python/ruff calls and environment mutations.
license: MIT
---

# Python Venv Execution

Ensure all Python execution and formatting strictly use the project's existing virtual environment. Global `python` and `ruff` calls are blocked by policy.

## Rules

1. **Interpreter Path:** Always use `.venv/bin/python`. Never use bare `python` or `python3`.
2. **Ruff From the Venv:** Always run Ruff as a module of the venv interpreter. Never use a host-installed Ruff or bare `ruff` on `PATH`, even if one is available. Run the formatter after every code change.
3. **No Environment Mutations:** Never run package installations or modify the environment. Assume dependencies, including Ruff, are already satisfied. If Ruff is missing from the venv, report it instead of installing it.

### Forbidden ❌
```bash
python main.py
python3 path/to/script.py
ruff format .
ruff check .
```

### Allowed ✅
```bash
.venv/bin/python main.py
.venv/bin/python path/to/script.py
.venv/bin/python -m ruff format .
.venv/bin/python -m ruff check .
```
