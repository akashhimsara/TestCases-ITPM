# IT23431676

This repository contains a Python automation script that opens the Chat Translator frontend, reads test cases from an Excel sheet, runs each input through the UI, and writes the actual output and pass/fail status back into the workbook.

## What it uses

- Python 3.10+
- [Playwright](https://playwright.dev/python/)
- [openpyxl](https://openpyxl.readthedocs.io/)

## Files

- [IT23431676.py](IT23431676.py) - main automation script
- [IT23431676.xlsx](IT23431676.xlsx) - sample Excel file in this repository

## Setup

Install the Python dependencies:

```bash
pip install playwright openpyxl
playwright install
```

## Usage

Run the script from the repository folder:

```bash
python IT23431676.py --excel IT23431676.xlsx
```

If your Excel file is inside another folder, pass the path explicitly:

```bash
python IT23431676.py --excel "test_automation/Assignment 1 - Test cases.xlsx"
```

## Command-line options

The script supports these useful arguments:

- `--excel` - input workbook path
- `--sheet` - worksheet name
- `--input-col` - column used for the source text
- `--expected-col` - column used for expected output
- `--actual-col` - column where actual output is written
- `--status-col` - column where pass/fail status is written
- `--url` - frontend URL to test
- `--output` - output workbook path
- `--headless` - run browser without a visible window

Example:

```bash
python IT23431676.py --excel IT23431676.xlsx --sheet "Test Cases" --headless
```

## Notes

- By default, the script targets `https://www.pixelssuite.com/chat-translator`.
- The script will create `Actual output` and `Status` columns if they are missing.
- Output is saved back to the same workbook unless `--output` is provided.