# Migration Evaluator Collector Export file Data Anonymizer and De-anonymizer

This Python script provides functionality to anonymize and de-anonymize ME Collector Export file containing inventory and usage data.

## Project Description

This tool is designed to protect sensitive information in inventory and usage data while allowing for analysis and later de-anonymization. It operates on Excel workbooks with multiple sheets containing data about asset utilization, ownership, and provisioning (both virtual and physical).

Key features include:

- Anonymization of Excel files by replacing human-readable names with randomly generated unique identifiers
- Removal of IP addresses from provisioning sheets
- De-anonymization of ME Quick Insights (QI) files using the original pre-anonymized data
- Command-line interface for easy integration into workflows

The anonymization process ensures that sensitive information like server names and IP addresses are removed or replaced, making the data safe for sharing or analysis. The de-anonymization feature allows authorized users to restore the original identifiers when needed, facilitating detailed insights and reporting.

## Repository Structure

<<<<<<< HEAD
- `collector-anonymizer.py`: The main Python script containing both anonymization and de-anonymization functions.
=======
- `collectoranonymizer.py`: The main Python script containing both anonymization and de-anonymization functions.
>>>>>>> 9b2484f (Initial commit)

## Usage Instructions

### Installation

Prerequisites:
- Python 3.6 or higher
- pip (Python package installer)

To install the required dependencies, run:

```bash
pip install openpyxl
```

### Anonymization

To anonymize an Excel file:

```bash
<<<<<<< HEAD
python collector-anonymizer.py an "path/to/your/excel_file.xlsx"
=======
python collectoranonymizer.py an "path/to/your/excel_file.xlsx"
>>>>>>> 9b2484f (Initial commit)
```

This will create a new file named "Inventory_And_Usage_Workbook Anonymized.xlsx" in the current directory.

### De-anonymization

To de-anonymize a Quick Insights (QI) zip file:

```bash
<<<<<<< HEAD
python collector-anonymizer.py de "path/to/original_excel_file.xlsx" "path/to/qi_file.zip"
=======
python collectoranonymizer.py de "path/to/original_excel_file.xlsx" "path/to/qi_file.zip"
>>>>>>> 9b2484f (Initial commit)
```

This will create new de-anonymized files with the prefix "deanonymized_" for each file in the QI zip.

### Common Use Cases

1. Preparing data for external analysis:
   ```bash
<<<<<<< HEAD
   python collector-anonymizer.py an "Inventory_Data.xlsx"
=======
   python collectoranonymizer.py an "Inventory_Data.xlsx"
>>>>>>> 9b2484f (Initial commit)
   ```

2. Restoring original identifiers after analysis:
   ```bash
<<<<<<< HEAD
   python collector-anonymizer.py de "Inventory_Data.xlsx" "QuickInsights_Results.zip"
=======
   python collectoranonymizer.py de "Inventory_Data.xlsx" "QuickInsights_Results.zip"
>>>>>>> 9b2484f (Initial commit)
   ```

### Troubleshooting

1. Issue: Script fails to run due to missing module
   - Error message: `ModuleNotFoundError: No module named 'openpyxl'`
   - Solution: Install the required module using `pip install openpyxl`

2. Issue: Incorrect file format
   - Error message: `zipfile.BadZipFile: File is not a zip file`
   - Solution: Ensure that the QI file for de-anonymization is a valid zip file

3. Issue: Permission denied when creating output files
   - Error message: `PermissionError: [Errno 13] Permission denied: 'output_file.xlsx'`
   - Solution: Ensure you have write permissions in the current directory

For further debugging:
- Run the script with the `-v` flag for verbose output
- Check the Python error traceback for specific line numbers and error types

## Data Flow

The data flow in this application follows these steps:

1. Input: Excel workbook (for anonymization) or Excel workbook + QI zip file (for de-anonymization)
2. Processing:
   - Anonymization: Replace names with IDs, remove IP addresses
   - De-anonymization: Map IDs back to original names
3. Output: New Excel file (anonymized) or CSV files (de-anonymized)

## Read More
https://aws.amazon.com/blogs/mt/anonymizing-sensitive-data-of-the-migration-evaluators-export-file/

<<<<<<< HEAD
## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

=======
>>>>>>> 9b2484f (Initial commit)
