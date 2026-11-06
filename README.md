# pa-permission-rogue-detector
Identifies permissions that deviate significantly from established organizational baselines or best practices. Uses statistical analysis and anomaly detection on permission assignments. The scan counts directories as well as files. A run with no baseline and without the SUID/SGID flag checks nothing and exits 1, a scan that finds no entries exits 1, and a failed report write exits 1. The output file must not overwrite the baseline file. - Focused on Tools for analyzing and assessing file system permissions

## Install
`git clone https://github.com/ShadowGuard-AI/pa-permission-rogue-detector`

## Requirements
Python 3 and the packages in requirements.txt (`pathspec` and `rich`).

## Usage
`python3 main.py -d /path/to/scan [-b baseline] [-e PATTERN ...] [-t THRESHOLD] [-o output] [--check-suid-sgid] [--no-color]`

## Parameters
- `-h`: Show help message and exit
- `-d`, `--directory`: (required) The directory to scan for permissions anomalies.
- `-b`, `--baseline`: Path to a file containing a baseline of acceptable permissions, one `permission,count` entry per line. If not provided, anomaly detection is skipped and only the SUID/SGID check runs when requested.
- `-e`, `--exclude`: File or directory patterns to exclude from the scan (e.g., `*.log` `temp_dir/*`). Uses gitignore-style patterns.
- `-t`, `--threshold`: Threshold for anomaly detection. Higher values mean less sensitivity. Defaults to 2.0.
- `-o`, `--output`: Path to output the rogue permissions report to a file (optional).
- `--check-suid-sgid`: Check for SUID/SGID bits set on files (potential privilege escalation risk).
- `--no-color`: Disable colored output.

## License
MIT License. See LICENSE.
