# AGENTS.md

## Cursor Cloud specific instructions

This is a **documentation-only repository** containing QA test cases for the "MEM" (Merchant Portal) product's Design Library module. It has no application source code, no dependencies, no build system, and no runnable services.

### Repository contents

- `README.md` — Project title only.
- `Design Library Test Cases.xlsx` — Manual QA test cases (2 sheets, ~95 rows total) covering the Design Library feature of the MEM merchant portal.

### Development notes

- There is **no code to lint, test, build, or run**.
- The Excel file can be read with Python's `openpyxl` library (pre-installed in the environment).
- Any future code additions should include their own dependency management and setup instructions.
