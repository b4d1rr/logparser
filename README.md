# LogParser

Logs are messy. Real messy.
Cloud systems spit out thousands of lines where some are perfectly formatted, some have extra spaces, and some are completely broken.
This project provides a fault-tolerant Python log parser designed to clean, validate, and structure log data before any analysis or reporting happens.

At its core, the parser transforms raw log lines into clean, structured Python objects — while safely ignoring anything that doesn’t follow the expected format.

🚀 What This Project Does

This repository contains a small but complete log-processing pipeline that can:

1. Parse individual log lines

Each line is expected to follow this structure:

timestamp | level | service | message

The parser:

Strips extra whitespace

Splits fields cleanly

Ensures the line has exactly 4 parts

Returns structured tuples

Returns None for broken/invalid lines

This ensures no crashes, even if the log file is a disaster.

2. Process lists or full log files

The parser can be applied to:

A single string

A list of log lines

A full .txt log file

Valid entries are extracted, bad ones are skipped — making downstream tasks safe and predictable.

3. Identify and count invalid log lines

Log files often contain:

Missing fields

Extra separators

Empty lines

Random garbage

The project includes a simple reporting tool that shows:

Total lines

Valid lines

Invalid format lines

This gives a quick quality check on the raw data.

4. Export clean logs to JSON

After parsing and filtering valid lines, the results can be exported to a clean, standardized JSON array:

[
  {
    "timestamp": "2026-02-05 08:11:20",
    "level": "ERROR",
    "service": "db",
    "message": "DB timeout"
  }
]

This makes the cleaned dataset ready for:

Dashboards

Log analysis tools

Further scripting

Integration with other systems

🧠 Why This Parser Matters

This project simulates a real-world operations problem:
Logs are the heartbeat of every backend system, but raw logs are rarely consistent.
Before filtering, monitoring, alerting, or analyzing — logs must be parsed safely.

This parser focuses on:

Defensive programming

Avoiding crashes on bad input

Strict formatting rules

Clean, predictable output

It’s a foundation you could easily extend with:

Log level validation

Timestamp checking

Error classification

Metrics dashboards

📂 Repository Structure
.
├── sample_logs.txt
├── parsed_logs.json           # output of the final export
├── task1_parse_single.py      # core parsing function
├── task2_parse_list.py        # parsing lists safely
├── task3_parse_file.py        # reading and parsing log files
├── task4_report_invalids.py   # statistics on bad lines
└── task5_export_parsed_json.py# JSON export tool
▶ Running the Project
python3 task1_parse_single.py
python3 task2_parse_list.py
python3 task3_parse_file.py
python3 task4_report_invalids.py
python3 task5_export_parsed_json.py
🔧 Tech Stack

Python 3.8+

No third-party libraries

Pure standard library (json, open(), etc.)
