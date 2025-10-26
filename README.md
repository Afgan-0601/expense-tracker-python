# expense-tracker-python

Personal Expense Tracker (Python)
=================================

A small, command-line personal expense tracker implemented in Python. It stores expenses in CSV files under the `data/` directory and keeps a monthly budget value in a separate CSV.

Project files
-------------
- `expense-tracker-app.ipynb` — Main notebook/script containing the expense tracker code and interactive menu.
- `data/expense-tracker.csv` — CSV file that stores expense records (date, category, amount, description).
- `data/budget.csv` — CSV file that stores a single `monthly_budget` value.

Data format
-----------
1. `data/expense-tracker.csv` has these columns: `date,category,amount,description`.
	 - Example rows from the repository:

```
date,category,amount,description
2025-10-25,Food,35.0,Lunch
2027-10-25,10,10.0,25djhbfherbfre
```

Note: The second example row contains a numeric category (`10`) and a seemingly-random description — this shows the CSV may contain varied or malformed user input. The app includes validation when adding new expenses but will load existing rows from the CSV.

2. `data/budget.csv` contains a header and a single `monthly_budget` value:

```
monthly_budget
400.0
```

How it works
------------
- On first run the app creates the `data/` directory and the CSV files (if missing) with headers.
- A simple interactive menu allows the user to:
	1. Add expense — prompts for date (YYYY-MM-DD), category (max 15 chars), amount (>0), and description (max 150 chars).
	2. View expenses — prints all loaded expenses in a table-like format.
	3. Track budget — compares sum of expenses to the monthly budget and warns if overspent.
	4. Save expenses — writes current in-memory expenses back to `data/expense-tracker.csv`.
	5. Exit — saves expenses and budget and exits.

Usage
-----
There are two common ways to run the tracker in this repo:

- Open and run the notebook `expense-tracker-app.ipynb` in Jupyter / VS Code. The main code is in the first code cell and includes the `main()` entrypoint.
- Or run the same Python script directly (if you prefer a .py file, you can export the notebook to a script) — from the project root:

```
python expense-tracker-app.py  # (if you export the notebook to a .py file)
```

Notes & suggestions
-------------------
- The app currently persists expenses by overwriting `data/expense-tracker.csv` when saving. Keep backups if you need versioning.
- The tracker includes input validation for new entries, but pre-existing CSV rows may contain unexpected values (see the example above). Consider cleaning old data if needed.
- Small improvements: add tests, convert the notebook into a package or CLI script, and add per-category/monthly reports or charts.

License
-------
This repository does not include a license file. Add a LICENSE if you intend to share or publish.

Contact
-------
For questions, open an issue or contact the repository owner.
