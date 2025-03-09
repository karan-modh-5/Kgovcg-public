# KGOVCG - Grandstream OpenVPN Configuration Generator

## Overview
`kgovcg` is a Python script designed to generate OpenVPN configuration files for Grandstream devices. It supports different VPN authentication types, validates IP addresses and ports, and organizes configuration files efficiently.

## Features
- Validates IP addresses and ports.
- Supports SSL VPN, User Authentication VPN, and a combination of both.
- Creates necessary directories and files for VPN configuration.
- Allows user input for site name and certificate details.
- Generates `.ovpn` configuration files dynamically.

## Requirements
- Python 3.x

## Installation
Clone this repository or download the `kgovcg.py` script:
```bash
git clone <repository-url>
cd <repository-folder>
```

## Usage
Run the script with optional arguments:
```bash
python kgovcg.py -i <OpenVPN_Server_IP> -p <OpenVPN_Port>
```
Options:
- `-v` : Display version information.
- `-i` : Specify OpenVPN server IP.
- `-p` : Specify OpenVPN port (default: 1194).

### Interactive Mode
If no arguments are provided, the script will prompt for user input.
```bash
python kgovcg.py
```
The script will ask for:
1. **Site Name**
2. **OpenVPN Server IP Address**
3. **OpenVPN Port** (default: 1194)
4. **VPN Type** (SSL, User Authentication, or both)
5. **Certificate and Key File Names** (if required)

Once completed, the `.ovpn` configuration file will be generated in the corresponding directory.

## Example
```bash
python kgovcg.py -i 192.168.1.1 -p 1194
```
Output:
```
Choose OpenVPN type by entering the corresponding number:
 1: SSL VPN
 2: User Authentication VPN
 3: SSL + User Authentication
Enter choice: 1
Folder 'kgovcg/site-name' created successfully.
File 'kgovcg/site-name/kgovcg.ovpn' created successfully!
```

## Notes
- Ensure the required certificate files exist before running the script.
- The script automatically creates directories if they do not exist.
- If no arguments are provided, the script will guide you through the setup interactively.
