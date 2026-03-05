
# Python Development Commands

## 1. Python Environment (pip / venv)

### Deactivate Current Environment

```bash
deactivate
```

Used when the current virtual environment is broken or no longer needed.

---

### Remove Old Virtual Environment

```bash
rm -rf myenv
```

Deletes the existing virtual environment folder.

---

### Create a New Virtual Environment

```bash
python3 -m venv venv
```

Creates a new virtual environment named `venv`.

---

### Activate Virtual Environment

```bash
source venv/bin/activate
```

Activates the environment so installed packages remain isolated.

---

### Upgrade pip

```bash
pip install --upgrade pip
```

Ensures you are using the latest version of `pip`.

---

### Install Project Requirements

```bash
pip install -r requirements.txt
```

Installs all dependencies listed in `requirements.txt`.

---

### Start Development Server (FastAPI)

```bash
uvicorn main:app --reload --port 8000
```

Explanation:

- `main` → Python file (`main.py`)
    
- `app` → FastAPI app instance
    
- `--reload` → Auto reload when code changes
    
- `--port 8000` → Runs server on port `8000`
    

---

# Python Environment (uv)

`uv` is a modern Python package manager that is **much faster than pip + venv**.

---

### Create Virtual Environment

```bash
uv venv
```

Creates a `.venv` environment.

---

### Activate Virtual Environment

```bash
source .venv/bin/activate
```

Activates the environment.

---

### Initialize Project

```bash
uv init
```

Creates project configuration files.

---

### Add a Package

```bash
uv add <package-name>
```

Example:

```bash
uv add fastapi
```

Adds a dependency and updates project files.

---

### Remove a Package

```bash
uv remove <package-name>
```

Example:

```bash
uv remove fastapi
```

Removes dependency from the project.

---

### Install / Sync Dependencies

```bash
uv sync
```

Installs all dependencies defined in the project configuration.

---

# Port Management Commands

Sometimes a port remains occupied by a crashed server.

### Kill Process Running on Port 8000

```bash
sudo lsof -t -i:8000 | xargs kill -9
```

Explanation:

- `lsof` → lists processes using the port
    
- `-t` → outputs process IDs only
    
- `kill -9` → force kills the process
    
