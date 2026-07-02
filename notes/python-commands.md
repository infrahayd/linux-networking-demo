# Python Virtual Environment

## Create a Virtual Environment

```bash
python -m venv .venv
```

Creates a virtual environment in the `.venv` directory.

Breakdown:

* `python` → Run the Python interpreter.
* `-m` → Run a Python module as a program.
* `venv` → Python's built-in virtual environment module.
* `.venv` → Directory where the virtual environment is created.

---

## Activate the Virtual Environment

### Linux

```bash
source .venv/bin/activate
```

After activation, your prompt should look similar to:

```text
(.venv) user@host:~/project$
```

This means any `python` or `pip` command now uses the virtual environment instead of the system Python.

---

## Install Packages

```bash
pip install fastapi uvicorn
```

Packages are installed only inside the active virtual environment.

---

## Save Installed Packages

```bash
pip freeze > requirements.txt
```

Creates `requirements.txt` containing every installed package and its version.

---

## Recreate the Environment

If someone clones your project:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

This recreates the same Python environment.

---

## Leave the Virtual Environment

```bash
deactivate
```

Returns to the system Python.

