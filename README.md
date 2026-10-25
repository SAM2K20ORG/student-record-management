# Student Record Management System

**Codomax Internship — Module 02: Functions, Files & Exception Handling**

A beginner-friendly command-line CRUD application using Python and JSON persistence. It uses only Python's standard library.

## Features
- Create student records
- List all students
- Search by student ID
- Update existing student details
- Delete records with confirmation
- Persist records in `students.json`
- Validate input and handle common file/JSON errors

Each record contains `id`, `name`, `age`, and `grade`.

## Requirements
- Python 3.10 or newer recommended
- No external dependencies

Check your version:
```bash
python --version
```
On some Linux systems, use `python3 --version`.

## Run locally
1. Download or clone this repository.
2. Open a terminal in this project directory.
3. Run:
   ```bash
   python main.py
   ```
   On Linux, if needed:
   ```bash
   python3 main.py
   ```

## Usage
Choose an option from the menu. Add a record with a unique student ID. Records are saved to `students.json` after successful create, update, and delete operations. Choose `6` to exit.

## Concepts demonstrated
- Functions, parameters, return values, and `next()` with a generator expression
- Dictionary/list data structures
- JSON file reading and writing
- `try`/`except` error handling
- Input validation and CRUD logic
- `if __name__ == "__main__"` entry point

## Test checklist
- [ ] Add a valid student
- [ ] Try adding a duplicate student ID
- [ ] List all students
- [ ] Search for an existing and a missing ID
- [ ] Update a student's grade and verify persistence after restart
- [ ] Cancel a delete, then confirm a delete
- [ ] Enter invalid age/grade and invalid menu choices
- [ ] Open the program after creating records to confirm JSON persistence

## Data and privacy
`students.json` is a local demonstration data file. Use fictional test data only; do not commit real students' personal information to a public repository.

## Suggested repository description
A Python CLI Student Record Management System demonstrating CRUD operations, JSON persistence, validation, and exception handling.
