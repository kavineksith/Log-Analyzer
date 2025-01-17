# Log Analyzer Script Documentation

## Overview
The Log Analyzer script is a Python-based utility designed to process and filter log files. It enables users to search through log files based on specific log levels and keywords, and subsequently export the filtered results to a new log file. This tool is ideal for administrators and developers who need to sift through large volumes of log data to extract relevant information.

## Features
- **Log Level Filtering**: Allows filtering log entries by predefined levels (`ERROR`, `INFO`, `WARN`).
- **Custom Search Parameters**: Provides the ability to specify search terms that must be present in the log entries.
- **Error Handling**: Includes comprehensive error handling for file access issues and invalid operations.
- **Export Functionality**: Facilitates the export of filtered log data to a specified file, appending data if the file already exists.
- **User-Friendly**: Designed to be run from the command line with clear error messages and usage instructions.

## Dependencies
- **Python 3**: The script is written in Python 3.x and requires a Python interpreter to run.
- **Standard Library Modules**:
  - `pathlib`: For handling file paths.
  - `sys`: For command-line argument parsing and exiting.
  - `re`: For regular expression operations.

No external libraries or packages are required beyond the standard Python library.

## Usage
To use the Log Analyzer script, follow these steps:

1. **Prepare the Log File**: Ensure that the log file you wish to analyze is available in the same directory as the script.

2. **Run the Script**: Execute the script from the command line with the following syntax:

   ```
   python log_analyzer.py <search_parameter> <log_level> <log_file> <export_file>
   ```
   - `<search_parameter>`: The term or terms to search for within the logs.
   - `<log_level>`: The log level to filter by (`ERROR`, `INFO`, `WARN`).
   - `<log_file>`: The name of the log file to analyze (excluding the `.log` extension).
   - `<export_file>`: The name of the file to which the filtered results will be written (excluding the `.log` extension).

### Example
To search for the term "network" in the `application` log file, filtering for `ERROR` level logs, and exporting the results to `filtered_logs`, use:

```
python log_analyzer.py network ERROR application filtered_logs
```

## Interactive Commands and Special Commands
- **`python log_analyzer.py`**: The primary command to execute the script.
- **`search_parameter`**: Provides the search terms for filtering log entries.
- **`log_level`**: Specifies the log level (`ERROR`, `INFO`, or `WARN`) to filter logs.
- **`log_file`**: The base name of the log file to read from (without the `.log` extension).
- **`export_file`**: The base name of the file to export filtered log data to (without the `.log` extension).

### Error Handling
- **File Access Issues**: The script handles errors such as `PermissionError` and `FileNotFoundError` gracefully, providing informative messages.
- **Unsupported Log Levels**: Raises a `ValueError` if an unsupported log level is specified.
- **Keyboard Interrupts**: Handles user interruptions (e.g., Ctrl+C) to exit gracefully.

## Conclusion
The Log Analyzer script is a powerful and user-friendly tool for managing and analyzing log files. Its capability to filter by log level and search parameters makes it highly effective for extracting meaningful information from large log datasets. By following the provided instructions, users can easily set up and run the script to tailor log data according to their needs, ensuring efficient log management and analysis.