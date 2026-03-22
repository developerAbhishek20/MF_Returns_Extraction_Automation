
Fund Survey Data Extraction Automation

This project automates the extraction of   Fund Survey data   from ZIP files containing Excel sheets.  
It consolidates key information such as   Fund Name, Month, and Total Portfolio Value   into a single Excel output file.

---

   🚀 Features
- Automatically scans a folder for ZIP files.
- Extracts Excel files inside each ZIP.
- Detects and processes the   Survey sheet   dynamically.
- Extracts:
  - Fund Name
  - Month
  - Total Portfolio Value
- Consolidates all extracted data into one Excel file.
- Handles missing or malformed files gracefully.

---

   ⚙️ Requirements
-   Python 3.8+  
- Microsoft Excel (optional, for viewing output)

    Python Libraries
Install required dependencies:
```bash
pip install pandas openpyxl
```

---

   📂 Project Structure
```
Fund-Survey-Automation/
│
├── automation_script.py         Main automation script
├── README.md                    Documentation
└── requirements.txt             Python dependencies
```

---

   🔧 Configuration
Update the following   paths   in the script before running:

```python
INPUT_FOLDER = r"C:\Users\asalvi\OneDrive - MORNINGSTAR INC\Documents\Automation Python\Raw Zip File"
OUTPUT_FOLDER = r"C:\Users\asalvi\OneDrive - MORNINGSTAR INC\Documents\Automation Python\Updated Excel File"
OUTPUT_FILE = os.path.join(OUTPUT_FOLDER, "Consolidated_Output.xlsx")
```

-   INPUT_FOLDER   → Folder containing ZIP files with Excel sheets.  
-   OUTPUT_FOLDER   → Folder where processed Excel will be saved.  
-   OUTPUT_FILE   → Final consolidated Excel file path.

---

   ▶️ Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Fund-Survey-Automation.git
   cd Fund-Survey-Automation
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Place your ZIP files in the   INPUT_FOLDER  .

4. Run the script:
   ```bash
   python automation_script.py
   ```

5. The script will:
   - Extract Excel files from ZIPs
   - Read Survey sheets
   - Collect Fund Name, Month, and Portfolio Value
   - Save consolidated results into `Consolidated_Output.xlsx`

---

   📊 Output Example
The final Excel file will look like:

| ZIP File       | Excel File   | Fund Name       | Month   | Total Portfolio Value |
|----------------|--------------|-----------------|---------|-----------------------|
| fund1.zip      | survey1.xlsx | ABC Growth Fund | Jan-26  | 123456.78             |
| fund2.zip      | survey2.xlsx | XYZ Equity Fund | Feb-26  | 987654.32             |

---

   ⚠️ Notes
- Script looks for sheets containing the word   "survey"  .
- If required labels (`Fund Name`, `Month`, `Total Portfolio`) are missing, the file is skipped.
- A small delay (`time.sleep(3)`) is added for OneDrive sync safety.
- Portfolio values are multiplied by 100 if stored as decimals.

---

   🛠️ Future Enhancements
- Add logging for better monitoring.
- Support CSV output.
- Handle multiple survey sheets per file.
- Add command-line arguments for flexibility.



