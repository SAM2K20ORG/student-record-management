# Codomax Internship — Module 02 Learning Notes
## Functions, Files & Exception Handling (Days 6–10)

### 1. Functions
Functions package reusable logic.

```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Sam"))
```

- **Parameter:** variable in a function definition.
- **Argument:** value passed when calling the function.
- **Return value:** result sent back with `return`.
- `print()` displays a value; `return` makes a value available to the caller.

### 2. Lambda functions
A `lambda` creates a small anonymous function with one expression.

```python
square = lambda number: number * number
print(square(5))  # 25
```

Prefer `def` for logic that needs a descriptive name, multiple statements, or documentation.

### 3. List comprehensions
A compact way to create lists from iterables.

```python
squares = [number * number for number in range(1, 6)]
evens = [number for number in range(10) if number % 2 == 0]
```

### 4. File handling
Use `with open(...)` so a file is closed automatically, including when an exception occurs.

```python
from pathlib import Path

path = Path("example.txt")
with path.open("w", encoding="utf-8") as file:
    file.write("Hello, Python!")

with path.open("r", encoding="utf-8") as file:
    print(file.read())
```

Common modes: `r` read, `w` write/overwrite, `a` append, `x` create only if absent. Choose UTF-8 explicitly for text.

### 5. CSV files
CSV is suitable for rows and columns. Use the `csv` module instead of manually splitting strings.

```python
import csv

with open("students.csv", "w", newline="", encoding="utf-8") as file:
    writer = csv.DictWriter(file, fieldnames=["id", "name", "age", "grade"])
    writer.writeheader()
    writer.writerow({"id": "S01", "name": "Example Student", "age": 20, "grade": 88.5})

with open("students.csv", newline="", encoding="utf-8") as file:
    for row in csv.DictReader(file):
        print(row)
```

CSV values are typically read as strings, so convert numeric fields when needed.

### 6. JSON files
JSON represents common data structures and is useful for small local projects.

```python
import json

record = {"id": "S01", "name": "Example Student", "grade": 88.5}
with open("student.json", "w", encoding="utf-8") as file:
    json.dump(record, file, indent=4)

with open("student.json", "r", encoding="utf-8") as file:
    loaded_record = json.load(file)
```

- `json.dump()` writes Python data to a file.
- `json.load()` reads JSON from a file.
- `json.dumps()` creates a JSON string.
- `json.loads()` parses a JSON string.
- Invalid JSON can raise `json.JSONDecodeError`.

### 7. Exception handling
Handle errors you can reasonably anticipate, and keep error messages useful.

```python
try:
    age = int(input("Age: "))
except ValueError:
    print("Enter a whole number.")
else:
    print("Valid age:", age)
finally:
    print("Input attempt finished.")
```

- `try`: code that may fail.
- `except`: handles a matching exception.
- `else`: runs when the `try` block succeeds.
- `finally`: runs whether an exception occurs or not.
- Avoid broad `except:` blocks that hide unexpected errors.
- Raise `ValueError` when a value is invalid for your function's contract.

### 8. Virtual environments
A virtual environment isolates project packages. This project has no third-party dependencies, but learning the workflow is useful.

Create:
```bash
python -m venv .venv
```
Activate on Windows PowerShell:
```powershell
.venv\Scripts\Activate.ps1
```
Activate on Linux/macOS:
```bash
source .venv/bin/activate
```
Deactivate:
```bash
deactivate
```

### 9. CRUD
CRUD means:
- **Create:** add a new record.
- **Read:** view or search records.
- **Update:** modify a record.
- **Delete:** remove a record.

The Student Record Management System uses student ID as a unique key and saves changes to JSON.

### 10. Debugging checklist
1. Read the full traceback, especially the last line.
2. Identify the line where the error occurs.
3. Check input types and variable names.
4. Test the smallest example that reproduces the issue.
5. Add boundary tests: empty input, missing ID, duplicate ID, invalid number, malformed JSON.
6. Re-run the program after each fix.

### 11. Mini exercises
1. Write a function `is_even(number)` returning a Boolean.
2. Use a list comprehension to make a list of cubes from 1 to 10.
3. Write a text file and read it back.
4. Read a CSV file and calculate the average of a numeric column.
5. Catch `ValueError` when converting user input to an integer.
6. Add a `find_student_by_name()` function to the project.

### 12. Before submitting
- Run each CRUD operation.
- Verify that records remain after closing and reopening the program.
- Try invalid input and confirm that the program does not crash.
- Add screenshots of the program running if the internship portal permits/requires them.
- Update the README with your own tested observations.
- Do not publish real student personal data.
