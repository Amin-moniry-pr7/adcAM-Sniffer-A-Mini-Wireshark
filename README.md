# 🔍 adcAM Sniffer v5.1

<div align="center">

![Version](https://img.shields.io/badge/version-5.1-blue.svg)
![Python](https://img.shields.io/badge/python-3.8+-green.svg)
![License](https://img.shields.io/badge/license-Non--Commercial-orange.svg)
![Status](https://img.shields.io/badge/status-active-success.svg)

**Advanced Network Packet Analysis & Security Testing Tool**

*Developed by Amin Moniry (adc7)*

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Screenshots](#-screenshots) • [Security](#-security) • [License](#-license)

---

</div>

## 🌟 Overview

**adcAM Sniffer** is a powerful, real-time network packet analyzer designed for security professionals, penetration testers, and network administrators. Built with Python and featuring a modern web-based interface, it provides deep insights into network traffic with advanced credential detection capabilities.

### 🎯 Key Highlights

- 🔴 **Real-Time Credential Detection** with instant red alert system
- 🌐 **Multi-Protocol Support** (HTTP, HTTPS, DNS, FTP, TCP, UDP, ARP)
- 📊 **Live Traffic Dashboard** with beautiful visualizations
- 🔐 **Enhanced Security** with bcrypt authentication
- 💾 **PCAP Export** for Wireshark compatibility
- 🎨 **Modern UI** with Nord color scheme
- ⚡ **High Performance** with multi-threading support

---

## ✨ Features

### 🕵️ Advanced Packet Analysis
- **Deep Packet Inspection**: Analyze all network layers (IP, TCP, UDP, Application)
- **Protocol Recognition**: Automatic detection of HTTP, HTTPS, DNS, FTP, and more
- **Domain Resolution**: Smart DNS cache and reverse lookup
- **Port Scanning Detection**: Track source and destination ports

### 🚨 Credential Detection System
- **Multi-Pattern Recognition**: Detects usernames, passwords, emails, tokens, and API keys
- **Real-Time Alerts**: Visual and sound notifications when credentials are found
- **Smart Filtering**: Eliminates false positives with intelligent validation
- **Export Capabilities**: Save detected credentials to TXT format

### 📈 Live Monitoring Dashboard
- **Real-Time Packet Stream**: See packets as they arrive
- **Protocol Statistics**: Top protocols and ports visualization
- **Session Summary**: Comprehensive traffic analysis
- **Display Filters**: Live filtering by IP, protocol, or domain

### 🔒 Security Features
- **User Authentication**: Secure login with bcrypt password hashing
- **Machine-Specific Licensing**: Activation code tied to hardware ID
- **Rate Limiting**: Protection against brute-force attacks
- **Database Encryption**: Secure storage of user credentials

### 💾 Export & Save
- **PCAP Files**: Export individual or all packets for Wireshark
- **Credential Reports**: TXT export of all detected sensitive data
- **Session Management**: Name and organize capture sessions

---

## 🚀 Installation

### Prerequisites

```bash
# Python 3.8 or higher
python --version

# Windows: Npcap (Required for packet capture)
# Download from: https://nmap.org/npcap/
```

### Step 1: Clone Repository

```bash
git clone https://github.com/Amin-moniry-pr7/adcAM-Sniffer.git
cd adcAM-Sniffer
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Install Npcap (Windows)

1. Download Npcap from [https://nmap.org/npcap/](https://nmap.org/npcap/)
2. Install with **WinPcap API-compatible Mode** enabled
3. Restart your computer

---

## 🎮 Usage

### Starting the Application

#### Windows (Administrator Required)
```bash
# Right-click Command Prompt → Run as Administrator
python run.py
```

#### Linux/Mac (Root Required)
```bash
sudo python3 run.py
```

### First-Time Setup

1. **Register an Account**
   - Click "Register" on the welcome screen
   - Enter username and password
   - Input your activation code
   - Click "Register"

2. **Login**
   - Enter your credentials
   - Click "Login"
   - Wait for the splash screen animation

3. **Select Network Interface**
   - Choose your active network adapter from the dropdown
   - Green dot indicates interface is up and running

### Basic Workflow

#### 1. **Set Capture Filter** (Optional)
   - Select a quick filter (HTTP, HTTPS, DNS, FTP, ICMP)
   - Or leave blank to capture all traffic

#### 2. **Start Sniffing**
   - Click the green **"▶ Start Sniffing"** button
   - Monitor live packets in the table
   - Watch for red-highlighted rows (credentials detected!)

#### 3. **Apply Display Filters**
   - Type in the "Display Filter" box to filter visible packets
   - Example: `192.168.1.1`, `http`, `google.com`

#### 4. **View Packet Details**
   - Click any packet row to open detail modal
   - Tabs: Summary | Layer Details | Raw Payload
   - Save individual packets as PCAP

#### 5. **Check Credentials Tab**
   - Red badge shows number of credentials found
   - View all detected sensitive data
   - Export credentials to TXT file

#### 6. **Export Data**
   - **Save All (PCAP)**: Export entire capture session
   - **Export Credentials (TXT)**: Save credential report
   - **Individual Packets**: Save specific packets

#### 7. **Stop & Clear**
   - Click **"■ Stop Sniffing"** to end capture
   - Use **"🗑️ Clear All"** to reset session

---

## 🎨 Interface Guide

### Main Dashboard Sections

```
┌─────────────────────────────────────────────────────────┐
│                  📊 adcAM Sniffer                       │
│            Real-time Traffic Analysis Dashboard         │
├─────────────┬───────────────────────────────────────────┤
│  Sidebar    │         Main Content Area               │
│             │                                           │
│ • Interface │  Tabs: Live Packets | Summary | Creds    │
│   Selector  │                                           │
│             │  [Packet Table with Real-Time Updates]   │
│ • Filters   │                                           │
│   - Display │                                           │
│   - Capture │                                           │
│   - Quick   │                                           │
│             │                                           │
├─────────────┴───────────────────────────────────────────┤
│  Status: Sniffing... | Packets: 1234 | [■ Stop]        │
└─────────────────────────────────────────────────────────┘
```

### Protocol Color Coding
- 🔴 **HTTP**: Red (Unencrypted traffic)
- 🟢 **HTTPS**: Green (Encrypted traffic)
- 🟠 **FTP**: Orange (File transfer)
- 🟣 **DNS**: Purple (Domain lookups)
- 🔵 **TCP**: Blue (General TCP)
- 🟡 **UDP**: Yellow (General UDP)

---

## 📸 Screenshots

### Welcome Screen
```
┌─────────────────────────────────┐
│         🎯 adcAM Sniffer        │
│   Please log in or register     │
│                                 │
│  [  Login  ] [  Register  ]    │
│                                 │
│  Username: ________________     │
│  Password: ________________     │
│                                 │
│         [ Login ]               │
└─────────────────────────────────┘
```

### Live Packet Capture
```
Time      Source           Destination      Protocol  Domain           Size
───────────────────────────────────────────────────────────────────────────
14:32:15  192.168.1.100:53 8.8.8.8:53      DNS       google.com       64
14:32:16  192.168.1.100:80 142.250.x.x:80  HTTP      example.com      512
14:32:17  192.168.1.100:443 31.13.x.x:443  HTTPS     facebook.com     1024
```

### Credential Alert
```
┌──────────────────────────────────────┐
│  🔒 Password Found                   │
│                                      │
│  Value: MyP@ssw0rd123                │
│  From: 192.168.1.100 → 10.0.0.50    │
└──────────────────────────────────────┘
```

---

## 🔧 Advanced Features

### BPF (Berkeley Packet Filter) Examples

```python
# Capture only HTTP traffic
"tcp port 80"

# Capture HTTP and HTTPS
"tcp port 80 or tcp port 443"

# Capture traffic from specific IP
"host 192.168.1.100"

# Capture DNS queries
"udp port 53"

# Capture FTP
"tcp port 21 or tcp port 20"

# Exclude certain IPs
"not host 192.168.1.1"

# Capture only TCP SYN packets
"tcp[tcpflags] & tcp-syn != 0"
```

### Display Filter Examples

```
# Filter by IP address
192.168.1.100

# Filter by protocol
http

# Filter by domain
facebook.com

# Filter by port (in Info column)
:443
```

---

## 🛡️ Security Considerations

### ⚠️ Important Warnings

1. **Legal Use Only**: Only use on networks you own or have explicit permission to test
2. **Administrator Rights**: Requires elevated privileges to capture packets
3. **Sensitive Data**: All captured credentials are stored locally
4. **Network Impact**: May cause increased network load during capture

### 🔐 Security Features

- **bcrypt Password Hashing**: Industry-standard password protection
- **Machine ID Binding**: Prevents unauthorized account sharing
- **Rate Limiting**: Protection against brute-force login attempts
- **Session Management**: Automatic timeout and secure session handling
- **Input Validation**: SQL injection and XSS protection

### 📋 Best Practices

- ✅ Always use on isolated test networks
- ✅ Clear sensitive data after testing
- ✅ Use strong passwords for registration
- ✅ Keep activation codes confidential
- ✅ Run antivirus scans regularly
- ✅ Update to latest version

---

## 🐛 Troubleshooting

### Common Issues

#### Issue: "No interfaces found"
**Solution**: 
- Run as Administrator (Windows) or sudo (Linux)
- Install Npcap/WinPcap
- Check if network adapters are enabled

#### Issue: "Failed to start sniffing"
**Solution**:
- Verify administrator privileges
- Check firewall settings
- Ensure Npcap is installed correctly
- Try different network interface

#### Issue: "Import Error"
**Solution**:
```bash
pip install --upgrade -r requirements.txt
```

#### Issue: Database locked
**Solution**:
- Close all instances of the application
- Delete `app_data.db` and restart
- Re-register your account

#### Issue: Browser not opening
**Solution**:
- Check if port 8080 is available
- Manually open: `http://localhost:8080`
- Install Chrome/Chromium browser

---

## 📊 Technical Specifications

### System Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| OS | Windows 10, Linux, macOS | Windows 11, Ubuntu 22.04 |
| Python | 3.8+ | 3.11+ |
| RAM | 2 GB | 4 GB+ |
| Disk Space | 100 MB | 500 MB |
| Network | Any NIC | Gigabit Ethernet |

### Dependencies

```
eel>=0.14.0          # GUI framework
scapy>=2.4.5         # Packet manipulation
psutil>=5.8.0        # System utilities
bcrypt>=3.2.0        # Password hashing
gevent>=21.0.0       # Async networking
bottle>=0.12.19      # Web server
```

### Architecture

```
adcAM-Sniffer/
│
├── app/
│   ├── __init__.py
│   └── application.py        # Core backend logic
│
├── web/
│   ├── index.html            # Main UI
│   ├── style.css             # Nord theme styling
│   ├── script.js             # Frontend logic
│   └── logo.ico              # Application icon
│
├── run.py                    # Entry point
├── requirements.txt          # Dependencies
├── LICENSE                   # Non-commercial license
├── .gitignore               # Git ignore rules
└── README.md                # This file
```

---

## 🎓 Educational Purpose

This tool is designed for:
- 📚 **Network Security Education**: Learn packet analysis
- 🔬 **Penetration Testing**: Authorized security assessments
- 🧪 **Research**: Academic network protocol studies
- 🛠️ **Development**: Testing network applications

### Learning Resources

- [Wireshark Documentation](https://www.wireshark.org/docs/)
- [Scapy Tutorial](https://scapy.readthedocs.io/)
- [BPF Filter Guide](https://biot.com/capstats/bpf.html)
- [Network Protocol Basics](https://www.cloudflare.com/learning/)

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Development Setup

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/adcAM-Sniffer.git

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

# Install dev dependencies
pip install -r requirements.txt

# Run tests (if available)
python -m pytest
```

---

## 📄 License

**Non-Commercial Use License v3.0**

Copyright © 2025 Amin Moniry (adc7). All rights reserved.

### ✅ Permitted Uses
- Personal, educational, and research purposes
- Non-profit organization activities
- Legitimate security testing and penetration testing
- Modification for non-commercial purposes

### ❌ Prohibited Uses
- Any commercial use or financial gain
- Selling, licensing, or commercializing the software
- Providing paid services using this software
- Integration into commercial products

For commercial licensing inquiries:
- 📧 Email: aminmoniry199@gmail.com
- 🌐 GitHub: [Amin-moniry-pr7](https://github.com/Amin-moniry-pr7)

---

## 📞 Contact & Support

### Get Help
- 🐛 **Bug Reports**: [Open an Issue](https://github.com/Amin-moniry-pr7/adcAM-Sniffer/issues)
- 💡 **Feature Requests**: [Submit Request](https://github.com/Amin-moniry-pr7/adcAM-Sniffer/issues)
- 📖 **Documentation**: Check this README

### Connect
- **Developer**: Amin Moniry (adc7)
- **Email**: aminmoniry199@gmail.com
- **GitHub**: [github.com/Amin-moniry-pr7](https://github.com/Amin-moniry-pr7)

---

## 🏆 Acknowledgments

Special thanks to:
- **Scapy Team** - Powerful packet manipulation library
- **Eel Project** - Seamless Python-JavaScript integration
- **Nord Theme** - Beautiful color scheme
- **Open Source Community** - Inspiration and support

---

## 📈 Version History

### v5.1 (Current) - 2025
- ✨ Enhanced credential detection with multi-pattern recognition
- 🚀 Improved performance with infinite scroll pagination
- 🎨 Modern UI with Nord color scheme
- 🔐 Enhanced security with bcrypt authentication
- 💾 Database storage for packet persistence
- 🐛 Bug fixes and stability improvements

### v5.0 - 2024
- 🎉 Complete UI redesign
- 📊 Real-time statistics dashboard
- 🔍 Advanced filtering capabilities

### v4.x - 2024
- Initial public release
- Basic packet capture functionality
- Credential detection system

---

## ⚡ Quick Start Cheatsheet

```bash
# 1. Install
git clone https://github.com/Amin-moniry-pr7/adcAM-Sniffer.git
cd adcAM-Sniffer
pip install -r requirements.txt

# 2. Run (as Admin/Root)
python run.py

# 3. Register → Login → Select Interface → Start Sniffing

# 4. Monitor credentials in real-time!
```

---

## 🌟 Star History

If you find this project useful, please consider giving it a ⭐ on GitHub!

---

<div align="center">

**Built with ❤️ by Amin Moniry**

*Making network security accessible to everyone*

[![GitHub](https://img.shields.io/badge/GitHub-Amin--moniry--pr7-blue?logo=github)](https://github.com/Amin-moniry-pr7)
[![License](https://img.shields.io/badge/License-Non--Commercial-orange)](LICENSE)
[![Version](https://img.shields.io/badge/Version-5.1-success)](https://github.com/Amin-moniry-pr7/adcAM-Sniffer)

---

**⚠️ Use Responsibly | 🔒 Security First | 📚 Education Focused**

</div>
