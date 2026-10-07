---
name: python-venv-execution
description: Enforces using the project's local virtual environment (.venv/bin/python) and forbids global python calls and environment mutations.
license: MIT
---

# Python Venv Execution

Ensure all Python execution strictly uses the project's existing virtual environment. Global `python` calls are blocked by policy.

## Rules

1. **Interpreter Path:** Always use `.venv/bin/python`. Never use bare `python` or `python3`.
2. **No Environment Mutations:** Never run package installations or modify the environment. Assume dependencies are already satisfied.

### Forbidden ❌
```bash
python main.py
python3 path/to/script.py
```

### Allowed ✅
```bash
.venv/bin/python main.py
.venv/bin/python path/to/script.py
```
