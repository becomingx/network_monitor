## Author: Patricia Tirado
Follow me on LinkedIn: 
www.linkedin.com/comm/mynetwork/discovery-see-all?usecase=PEOPLE_FOLLOWS&followMember=patriciatirado29a
'Forging better outcomes with uncommon sense".

## Network Monitor
A simple proof of concept Python-based network monitor that periodically pings a target host and logs the status and latency to a .txt file. 
Designed for simplicity and modularity.

## Features
* Pings a target host (default: Google DNS 8.8.8.8)
* Logs status (Success, Failed, Timeout, or error) and latency to network_log.txt
* Modular logging via logger_helper.py
* Cross-platform support (Windows, macOS, Linux)
* Graceful error handling and user-friendly console output

## Requirements
* Python 3.6+
* On some systems, you may need to run with elevated privileges to access network interfaces.

## Dependencies:
* No external dependencies (uses built-in modules and subprocess)

## File Structure
├── network_monitor.py       # Main monitoring script
├── logger.py                # Logging helper module
├── network_log.txt          # Output log file (auto-created)
├── README.md                # Project documentation

## Configuration
You can modify these constants in network_monitor.py:
TARGET = "8.8.8.8"       # Host to ping (Default is Google DNS 8.8.8.8)
LOG_FILE = "network_log.txt"  # Log file path
INTERVAL = 5             # Seconds between pings (Default is 5 seconds)

## How It Works
* Ping Execution: Uses subprocess.run() to ping the target once.
* Latency Parsing: Extracts latency from the ping output, if available.
* Logging: Delegates logging to module logger_helper.log_to_file(), which appends timestamped entries to network_log.txt.

## Sample Output
Console:
2025-08-13 15:38:00 | Status: Success | Latency: 23.0 ms
2025-08-13 15:38:05 | Status: Success | Latency: 22.0 ms
Log file (network_log.txt):

2025-08-13 15:38:00 | Status: Success | Latency: 23.0 ms
2025-08-13 15:38:05 | Status: Success | Latency: 22.0 ms

## Running the Monitor
* Open Bash terminal and type:
  python network_monitor.py
* Press Enter to run

## TODOs:
* Ask user for input on: TARGET, INTERVAL, or offer choice to continue with defaults
* Ask user to specify name and save location of log file, or continue with defaults
* Support structured logging (CSV or JSON)
* Add alerting for repeated failures or high latency
* Visualize logs with a simple dashboard
