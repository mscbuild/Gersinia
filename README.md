# Gersinia - testing network protocols and generating packets

 ![Username](https://komarev.com/ghpvc/?username=mscbuild)
 [![Author](https://img.shields.io/badge/Author-Yuri%20Dev-blue.svg)](http://mscbuild.github.io/)
 ![](https://img.shields.io/badge/PRs-Welcome-green)
 ![](https://img.shields.io/github/languages/code-size/mscbuild/Gersinia)
![](https://img.shields.io/badge/code%20style-python-green)
![](https://img.shields.io/github/stars/mscbuild)
![](https://img.shields.io/badge/Topic-Github-lighred)
![](https://img.shields.io/website?url=https%3A%2F%2Fgithub.com%2Fmscbuild)

The Gersinia tool takes advantage of known weaknesses in several network protocols.It helps with trying to abuse the weaknesses to ensure that network protections are implemented where possible.

## Screenshots

<img width="1366" height="722" alt="456" src="https://github.com/user-attachments/assets/f45c1d2e-e8c3-4fa1-8f11-495dca34e0a2" />
<img width="1366" height="718" alt="457" src="https://github.com/user-attachments/assets/f7bc9d6b-f5fe-41b4-a913-aa7a6a7ca0cd" />
 


A modern GUI application for network protocol testing and packet crafting, similar to Yersinia but with updated functionality and a user-friendly interface.

## Features

- **ARP Spoofing**: Perform ARP cache poisoning attacks between targets
- **DHCP Starvation**: Exhaust DHCP server resources with fake requests
- **LLMNR Spoofing**: Intercept and respond to LLMNR queries
- **Packet Crafting**: Create custom network packets with various protocols
- **Modern GUI**: Built with CustomTkinter for a clean, dark-themed interface
- **Real-time Logging**: Monitor all activities with timestamped output

## Requirements

- Python 3.7+
- Administrator/root privileges (required for packet crafting and network attacks)
- Dependencies listed in `requirements.txt`

## Installation

1. Clone or download the project:
```bash
git clone https://github.com/mscbuild/Gersinia
cd Gersinia
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Running the Application

**Windows:**
```cmd
# Run as Administrator
python main.py
```

**Linux/macOS:**
```bash
# Run as root
sudo python3 main.py
```

### Attack Modules

#### ARP Spoofing
1. Select a network interface
2. Enter target IP address
3. Enter gateway IP address
4. Click "Start ARP Spoof"
5. Monitor output for attack progress

#### DHCP Starvation
1. Select a network interface
2. Set the number of DHCP requests (default: 100)
3. Click "Start DHCP Starvation"
4. Watch as DHCP leases are exhausted

#### LLMNR Spoofing
1. Select a network interface
2. Enter your attacker IP address
3. Click "Start LLMNR Spoof"
4. The tool will respond to LLMNR queries with your IP

### Packet Crafting

1. Click the "Packet Crafter" button
2. Add layers to your packet:
   - **Ethernet**: Configure MAC addresses and EtherType
   - **IP**: Set source/destination IPs, TTL, protocol
   - **TCP**: Configure ports, sequence numbers, flags
   - **UDP**: Set source/destination ports
   - **ARP**: Configure ARP request/response parameters
   - **ICMP**: Set type, code, ID, and sequence
3. Click "Build Packet" to construct the packet
4. Preview the packet structure in the preview window
5. Configure send options (count and interval)
6. Click "Send Packet" to transmit

### Packet Templates

- **Save Template**: Save current packet configuration as JSON
- **Load Template**: Load previously saved packet configurations
- Templates are stored as JSON files for easy sharing and modification

## Network Interface Selection

The tool automatically detects available network interfaces:
1. Use the dropdown to select your active network interface
2. Click "Refresh Interfaces" if you change network connections
3. The selected interface is used for all attacks and packet sending

## Logging and Output

- All activities are logged in the main output window
- Logs include timestamps and detailed information
- Activities are also saved to `network_attack_tool.log`
- Use "Clear Output" to reset the display

## Security Considerations

**IMPORTANT**: This tool is designed for:
- Educational purposes and security research
- Network penetration testing with proper authorization
- Understanding network protocol vulnerabilities

**Do NOT use for:**
- Unauthorized network access
- Malicious activities
- Violating laws or organizational policies

Always ensure you have:
- Explicit permission to test networks
- Proper authorization for penetration testing
- Understanding of legal and ethical implications

## Troubleshooting

### Common Issues

1. **"Administrator privileges required"**
   - Windows: Right-click and "Run as administrator"
   - Linux/macOS: Use `sudo` or run as root

2. **"No network interfaces found"**
   - Check network adapter is enabled
   - Try refreshing interfaces
   - Ensure you have network connectivity

3. **Packet sending fails**
   - Verify network interface is correct
   - Check firewall settings
   - Ensure administrator privileges

4. **LLMNR spoofing not working**
   - LLMNR queries may be disabled on target network
   - Check if port 5355 is blocked
   - Verify target is using Windows name resolution

## Development

### Project Structure
```
network_attack_tool/
├── main.py              # Main application and GUI
├── packet_crafter.py    # Packet crafting module
├── requirements.txt     # Python dependencies
└── README.md           # This file
```

### Adding New Attacks
1. Create attack method in `main.py`
2. Add GUI controls in `create_widgets()`
3. Implement toggle method for start/stop
4. Add logging for attack status

### Protocol Support
The tool supports common network protocols:
- Ethernet II
- IPv4
- TCP/UDP
- ARP
- ICMP
- DHCP
- LLMNR/NetBIOS
- DNS (basic support)

## Why it's used

**The Gersinia tool helps network administrators and security professionals:**

- Test network resilience to Layer 2 attacks.
 
- Demonstrate vulnerabilities that are often overlooked during security assessments (usually focused on Layer 3/L4).
 
- Test security settings: Port Security, DHCP Snooping, Dynamic ARP Inspection.

## License

This project is for educational and research purposes. Users are responsible for compliance with applicable laws and regulations.

## Contributing

Contributions are welcome for:
- New attack modules
- Protocol support
- UI improvements
- Bug fixes
- Documentation updates

> [!WARNING]  
> Please ensure all contributions maintain ethical use guidelines.
 
✅ No vulnerable dependencies detected.
