# SLR_rem_duplicates
Systematic Literature Review: Automatic duplicate removal using bibliometric data from **Web of Science**, **Scopus**, and **ProQuest**.

**Note:** Not all duplicates may be removed due to small deviations in formatting.

---

## Features

- Reads bibliometric data from **Web of Science**, **Scopus**, and **ProQuest**.
- Supports data in **CSV** and **Excel** file formats.
- Standardizes columns and cleans string data (e.g., removes special characters, converts to lowercase).
- Merges datasets into a unified format.
- Removes duplicates based on `Authors`, `Title`, and `Year`.
- Outputs summary statistics:
  - Number of studies before and after deduplication.
  - Number of duplicates removed.
  - Count of studies per data source.
- Displays the final deduplicated dataset.

---

## Prerequisites

- Python 3.7 or higher
- The following Python libraries:
  - `pandas`
  - `unidecode`
  - `warnings`

---

## How to Use

1. **Prepare Your Data**
   - Ensure your datasets are in **CSV** or **Excel** format.
   - Datasets should contain bibliometric information such as `Authors`, `Title`, `Year`, and `Citations`.

2. **Provide File Paths**
   - In the code, assign the file paths of your datasets to the following variables:
     ```python
     FILE_PATH_WOS = "" # Web of Science dataset
     FILE_PATH_SD = ""  # Scopus dataset
     FILE_PATH_PQ = ""  # ProQuest dataset
     ```
     **Note:** The code only supports **CSV** and **Excel** formats for the bibliometric data.

3. **Run the Jupyter Notebook**
   - Open the notebook.
   - Execute all cells in the notebook sequentially.

4. **View the Results**
   - The notebook will display:
     - Summary statistics for the dataset before and after deduplication.
     - Number of duplicates removed.
     - Count of studies from each source.
     - The complete deduplicated dataset.

---

## Code Overview

### Key Functions

1. **File Reading**
   - `read_file`: Reads a single file (CSV or Excel) into a Pandas DataFrame.
   - `read_files`: Reads datasets for all three sources based on file paths.

2. **Data Preprocessing**
   - `adjust_wos`: Preprocesses Web of Science data.
   - `adjust_scopus`: Preprocesses Scopus data.
   - `adjust_proquest`: Preprocesses ProQuest data.

3. **Data Merging and Deduplication**
   - `merge_dfs`: Combines the cleaned datasets into a single DataFrame.
   - `rem_duplicates`: Removes duplicate studies and provides statistics.

4. **Workflow Management**
   - `main`: Orchestrates the entire workflow from file reading to summary generation.

---

## Customization

1. **Add New Data Sources**
   - Extend the preprocessing functions to handle additional datasets with different structures.

2. **Export Results**
   - Save the deduplicated dataset to a file:

3. **Modify Deduplication Logic**
   - Customize the criteria for identifying duplicates by editing the `rem_duplicates` function.

---

## Notes

- Not all duplicates may be removed due to small deviations in formatting.
