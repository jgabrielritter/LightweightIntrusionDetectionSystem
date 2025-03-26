# Lightweight Intrusion Detection System (IDS)

## Overview

This Lightweight Intrusion Detection System (IDS) is a Python-based network monitoring tool designed to detect potential security threats such as SYN flood attacks and port scanning activities. The application provides a graphical user interface (GUI) for easy configuration and real-time alert monitoring.

## Features

- Real-time network packet monitoring
- Graphical user interface for easy interaction
- Configurable threat detection thresholds
- IP whitelisting and blacklisting
- Alerts for:
  - SYN flood attacks
  - Port scanning activities
- Logging of detected threats
- Configurable network interface selection

## Prerequisites

### Required Libraries
- scapy
- tkinter
- logging
- threading
- queue
- json
- os

### System Requirements
- Python 3.7+
- Linux or macOS (recommended for network monitoring)
- Root/Administrator privileges for packet capturing

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/lightweight-ids.git
cd lightweight-ids
```

2. Install required dependencies:
```bash
pip install scapy
```

## Usage

### Running the Application

```bash
python lightweight_ids.py
```

### GUI Components

#### Network Interface Section
- Select the network interface to monitor
- Start/Stop monitoring button

#### Configuration Section
- Whitelist and Blacklist IP addresses
- Configure detection thresholds:
  - SYN Flood Threshold
  - SYN Flood Window
  - Port Scan Unique Ports
  - Port Scan Window
- Save and Load configuration options

#### Alerts Section
- Real-time display of detected threats
- Clear alerts functionality

## Configuration File

The application uses a `ids_config.json` file for persistent configuration. You can manually edit this file or use the GUI's save/load configuration features.

Example configuration:
```json
{
  "whitelist_ips": ["192.168.1.100", "10.0.0.1"],
  "blacklist_ips": ["123.45.67.89"],
  "syn_flood_threshold": 100,
  "syn_flood_window": 10,
  "port_scan_unique_ports": 10,
  "port_scan_window": 60
}
```

## Threat Detection Algorithms

### SYN Flood Detection
- Monitors the number of SYN packets from a single IP
- Configurable threshold and time window
- Generates an alert if the threshold is exceeded

### Port Scan Detection
- Tracks unique destination ports from a single source IP
- Configurable unique port threshold and time window
- Generates an alert if the threshold is exceeded

## Logging

- Alerts are logged to `ids_alerts.log`
- Log format: `timestamp - log_level: message`

## Security Considerations

- Requires root/administrator privileges
- Use with caution on production networks
- Customize configuration to match your network's specific requirements

## Limitations

- Works best on Linux/macOS
- Requires network interface name for monitoring
- Basic threat detection capabilities

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## Disclaimer

This tool is for educational and research purposes. Always obtain proper authorization before monitoring network traffic.
