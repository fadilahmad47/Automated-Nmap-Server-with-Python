# 🔍 Automated Nmap Server Scanner

A lightweight Python script that performs rapid Nmap scans on a target IP every 60 seconds, logging results to timestamped files. Perfect for continuous port monitoring on servers, labs, or test environments.

[![Python](https://img.shields.io/badge/python-3.x-blue.svg)](https://www.python.org/) [![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

## ⚡ Key Features

- **Rapid Scans**: Uses Nmap's `-T4 -F` flags for quick, top-ports discovery—runs every 60 seconds (customizable via the script's sleep interval).
- **Automated Logging**: Outputs each scan to a dated `.txt` file in a dedicated directory.
- **Easy Setup**: Auto-creates the output folder; simple config for target IP and save path.
- **Verbose Logging**: Console feedback for each run, with timestamps for tracking.
- **Portable Code**: Clean, modular structure ideal for beginners and pros alike.

## 🎯 Quick Start

### Prerequisites

- Python 3.x
- [Nmap](https://nmap.org/download.html) installed and accessible in your PATH
- Linux/macOS (preferred) or Windows via WSL/VM for best compatibility

### Installation & Run

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/automated-nmap-server-scanner.git
   cd automated-nmap-server-scanner
   ```

2. **Configure the Script**:
   - Open `server_nmap_scanner.py` in your editor (e.g., `nano server_nmap_scanner.py`).
   - Set your target IP:
     ```python
     target_ip = "192.168.1.1"  # Replace with your server's IP
     ```
   - Adjust the output directory (near the top of the script):
     ```python
     output_dir = "/home/yourusername/Desktop/nmap_scan_server/"  # Customize to your path
     ```

3. **Launch the Scanner**:
   ```bash
   python3 server_nmap_scanner.py
   ```
   - **Note**: For full Nmap access (e.g., raw sockets), run with elevated privileges:
     ```bash
     sudo python3 server_nmap_scanner.py
     ```
   - Press `Ctrl+C` to stop and review logs.

### Sample Output Structure

The script generates files like this in your specified directory:

```
nmap_scan_server/
├── serverscan_2025-11-16_23-49-00.txt
├── serverscan_2025-11-16_23-50-00.txt
└── ... (one per scan interval)
```

Each file captures the complete Nmap output, including open ports, services, and versions.

## 📝 Usage Tips

- **Customize Interval**: Edit the `time.sleep(60)` line at the script's end to scan more/less frequently (e.g., 30 for every half-minute).
- **Target Selection**: Use IPs in your local network or lab setup—avoid scanning without permission!
- **Analysis**: Grep files for patterns (`grep "open" *.txt`) or pipe to tools like `awk` for summaries.
- **Troubleshooting**: If Nmap fails, check permissions or verify installation with `nmap --version`.

## 🤝 Contributing

Love the tool? Fork it, tweak it (e.g., add JSON output or email alerts), and open a PR! Check [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines. Issues and stars are always appreciated.

## 📄 License

MIT License—free to use, modify, and distribute. See [LICENSE](LICENSE) for details.


---

⭐ **Star this repo** if it saves you time—questions? Drop an issue!
