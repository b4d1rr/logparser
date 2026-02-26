PL202 — Week 4: Log Line Parser

This project implements a safe and reliable log line parser using Python.
It processes individual log lines, lists, and entire files, reports invalid formats, and exports valid parsed entries to JSON.

📌 Project Overview

Cloud operations teams receive messy log files.
Your task is to safely parse each log line into four fields:

timestamp | level | service | message

A valid parsed line becomes a tuple:

(timestamp, level, service, message)

If the line is broken or not in the correct format → it is marked invalid.

📁 Project Structure
.
├── task1_parse_single.py
├── task2_parse_list.py
├── task3_parse_file.py
├── task4_report_invalids.py
├── task5_export_parsed_json.py
├── sample_logs.txt
└── parsed_logs.json        # generated in Task 5
📝 Task Breakdown
Task 1 — Parse a Single Line

Implement parse_log_line(line)

Strip spaces, split on "|", ensure exactly 4 fields

Return parsed tuple or None for invalid lines

Task 2 — Parse a List of Lines

Use parse_log_line for each line in a Python list

Skip invalid lines

Return a list of valid parsed tuples

Task 3 — Parse a Log File

Read sample_logs.txt line-by-line

Parse each line

Print the first 5 valid parsed results

Task 4 — Report Invalid Format Lines

Read the file

Count:

Total lines

Valid lines

Invalid format lines

Print exactly:

Total lines: X
Valid lines: Y
Invalid format lines: Z
Task 5 — Export Parsed Results to JSON

Parse file

Keep only valid lines

Export as:

[
  {"timestamp": "...", "level": "...", "service": "...", "message": "..."},
  ...
]

Saved to: parsed_logs.json

▶ How to Run
python3 task1_parse_single.py
python3 task2_parse_list.py
python3 task3_parse_file.py
python3 task4_report_invalids.py
python3 task5_export_parsed_json.py
⚙ Requirements

Python 3.8+

No external dependencies

📄 License

MIT (optional — add only if needed)
