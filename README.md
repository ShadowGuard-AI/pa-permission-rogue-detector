# pa-permission-rogue-detector
Identifies permissions that deviate significantly from established organizational baselines or best practices. Uses statistical analysis and anomaly detection on permission assignments. The scan counts directories as well as files. A run with no baseline and without the SUID/SGID flag checks nothing and exits 1, a scan that finds no entries exits 1, and a failed report write exits 1. The output file must not overwrite the baseline file. - Focused on Tools for analyzing and assessing file system permissions

## Install
`git clone https://github.com/ShadowGuardAI/pa-permission-rogue-detector`

## Usage
`./pa-permission-rogue-detector [params]`

## Parameters
- `-h`: Show help message and exit
- `-d`: The directory to scan for permissions anomalies.
- `-b`: Path to a file containing a baseline of acceptable permissions.  
- `-e`: File or directory patterns to exclude from the scan (e.g., 
- `-t`: Threshold for anomaly detection. Higher values mean less sensitivity. Defaults to 2.0.
- `-o`: No description provided
- `--check-suid-sgid`: No description provided
- `--no-color`: Disable colored output.

## License
Copyright (c) ShadowGuardAI
