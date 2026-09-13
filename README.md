# Network Sniffer

[![Tests](https://github.com/abdulrhmansaad456eg/CodeAlpha_BasicNetworkSniffer/actions/workflows/tests.yml/badge.svg)](https://github.com/abdulrhmansaad456eg/CodeAlpha_BasicNetworkSniffer/actions/workflows/tests.yml)


A desktop packet capture tool built with Python and CustomTkinter, made for learning how network traffic actually works. It grabs live packets off the wire, breaks them down by protocol, and shows everything in a filterable interface.

Note: capture performance depends on how busy the network is, and on Windows you'll need admin rights.

![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)
![Platform](https://img.shields.io/badge/Platform-Windows%2011-purple.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

---

## Overview

This is a cybersecurity portfolio project. It captures live network traffic and presents it in an organized, searchable interface, covering the common protocols you run into day to day.

---

## Features

### Live Packet Capture
- Real-time packet sniffing using Scapy
- Non-blocking threaded capture engine
- Automatic packet parsing and classification
- Support for TCP, UDP, ICMP, and HTTP traffic

### Protocol Analysis
- **TCP**: header inspection with flag analysis
- **UDP**: port and payload examination
- **ICMP**: type and code interpretation
- **HTTP**: request/response detection and parsing

### Interactive Controls
- Start/Stop capture
- Protocol filtering (TCP, UDP, ICMP, ALL)
- Search across all packet fields
- Real-time statistics dashboard

### Data Management
- Export captured packets to JSON or TXT with a custom save location
- Persistent log storage
- Clear data functionality
- Packet details inspection dialog

### UI
- Dark themed interface
- CustomTkinter for native Windows styling
- Responsive layout that adapts to window size

---

## Screenshots

### Main Interface
![Main Interface](screenshots/main_interface.png)

### Packet Details View
![Packet Details](screenshots/packet_details.png)

---

## Installation

### Prerequisites
- Windows 11 (primary target platform)
- Python 3.11 or higher
- Administrator privileges (required for packet capture)
- Npcap or WinPcap driver

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/abdulrhmansaad456eg/CodeAlpha_BasicNetworkSniffer.git
   cd CodeAlpha_BasicNetworkSniffer
   ```

2. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Install Npcap (if not already installed)**
   - Download from https://npcap.com/
   - Run the installer with "WinPcap API-compatible Mode" enabled
   - Restart your computer

4. **Run the application**
   ```bash
   # Open the terminal as administrator first
   python main.py
   ```

---

## Usage

### Starting a Capture
1. Launch the application as administrator
2. Select a protocol filter (default: ALL)
3. Click "Start Capture"
4. Packets appear in real time

### Analyzing Packets
- Double-click any packet to view detailed information
- Use the search bar to filter by IP, port, or payload content
- Check the stats cards for protocol distribution

### Exporting Data
1. Click "Export Data" in the sidebar
2. Pick a format (JSON or TXT)
3. Click "Confirm Export"
4. Choose a save location in the file picker

### Keyboard Shortcuts
- `Enter` on a selected packet opens its details
- The search bar filters live as you type

---

## Technologies Used

| Component | Technology |
|-----------|------------|
| Language | Python 3.11+ |
| Packet Capture | Scapy 2.5+ |
| GUI Framework | CustomTkinter |
| Utilities | psutil, Pillow |

---

## What I Learned

- **Network protocols**: how the TCP/IP stack fits together, packet structures, protocol behavior
- **Scapy**: packet capture and parsing in practice
- **Threading**: running capture in the background without freezing the UI
- **Desktop UI development**: building a responsive interface with CustomTkinter
- **Error handling**: permission issues, driver dependencies, network errors
- **Data processing**: parsing and filtering a live stream of packets

---

## Project Structure

```
CodeAlpha_BasicNetworkSniffer/
├── core/
│   ├── sniffer.py          # Packet capture engine
│   ├── packet_parser.py    # Packet analysis utilities
│   ├── filters.py          # Search and filter logic
│   └── exporter.py         # Export functionality
├── ui/
│   ├── main_window.py      # Main application window
│   ├── widgets.py          # Custom UI components
│   ├── styles.py           # Theme and styling
│   └── dialogs.py          # Popup dialogs
├── tests/                  # Unit tests
├── screenshots/            # Application screenshots
├── main.py                 # Entry point
├── requirements.txt        # Dependencies
└── README.md
```

---

## Troubleshooting

### "No permission to capture packets"
Run the application as administrator. Packet capture requires elevated privileges on Windows.

### "Npcap not found"
Install Npcap from https://npcap.com/ and restart your computer.

### "No traffic appearing"
- Check your network connection
- Generate some traffic: open a browser, ping a website
- Verify firewall settings

### Application crashes on start
- Make sure all dependencies are installed: `pip install -r requirements.txt`
- Check your Python version (3.11+ required)

---

## Future Improvements

- [ ] Packet capture to PCAP file format
- [ ] Protocol-specific analysis views
- [ ] Network graph visualization
- [ ] Rule-based alerting system
- [ ] Historical trend analysis
- [ ] Cross-platform Linux support
- [ ] Plugin system for custom protocols

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Project Link: [https://github.com/abdulrhmansaad456eg/CodeAlpha_BasicNetworkSniffer](https://github.com/abdulrhmansaad456eg/CodeAlpha_BasicNetworkSniffer)
