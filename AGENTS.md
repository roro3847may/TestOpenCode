# Agent Guidelines for TestOpenCode

This document provides essential instructions for AI agents operating in this repository. Adhere to these standards to ensure consistency and high-quality code.

## 1. Development Environment
- **Language:** Python 3.12+
- **IDE:** PyCharm (Pre-configured with `.idea` files)
- **Virtual Environment:** `.venv/` (Located in the root directory)
- **Package Manager:** `pip` (Use `pip install` for new dependencies)

## 2. Core Commands

### 2.1 Build & Setup
To set up the environment, run:
```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
pip install -r requirements.txt
```

### 2.2 Testing
We use `pytest` for testing.
- **Run all tests:** `pytest`
- **Run a single test file:** `pytest tests/test_file.py`
- **Run a specific test case:** `pytest tests/test_file.py::test_function_name`

### 2.3 Linting & Formatting
- **Linter:** `ruff check .`
- **Formatter:** `ruff format .`
Please run these before creating any Pull Request.

## 3. Code Style Guidelines

### 3.1 Imports
Follow PEP 8 grouping:
1. Standard library imports.
2. Related third-party imports.
3. Local application/library specific imports.

Example:
```python
import os
import sys

import requests
from flask import Flask

from my_module import my_function
```

### 3.2 Type Hinting
All function signatures **must** include type hints for parameters and return types.
```python
def calculate_sum(a: int, b: int) -> int:
    return a + b
```

### 3.3 Naming Conventions
- **Modules/Packages:** `snake_case` (e.g., `data_processor.py`)
- **Classes:** `PascalCase` (e.g., `UserAccount`)
- **Functions/Variables:** `snake_case` (e.g., `get_user_id`)
- **Constants:** `UPPER_SNAKE_CASE` (e.g., `MAX_RETRY_COUNT`)

### 3.4 Error Handling
- Never use bare `except:`.
- Catch specific exceptions and log the error context.
- Use `logger.exception()` when re-raising or handling critical failures.

```python
try:
    result = perform_action()
except ConnectionError as e:
    logger.error(f"Failed to connect: {e}")
    raise
```

## 4. Documentation
- Write docstrings in **English**.
- Use the **Google Python Style** for docstrings.
- Chat communications and plan descriptions should be in **Korean**.

## 5. Agent Workflow Rules
1. **Read Before Write:** Always read the file content using the `read` tool before attempting an `edit`.
2. **Atomic Commits:** Make small, logical commits with clear descriptions in English.
3. **Verification:** Always run `pytest` (if available) after making changes to ensure no regressions.
4. **No Chitchat:** Keep responses concise. Focus on the plan and execution.

---
*This file is generated for agentic workflows. Update as the project evolves.*
