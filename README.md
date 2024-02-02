# WiFi Cracking Lab Summary

This document provides an overview of the commands and steps involved in the lab exercise for cracking WiFi passwords. This exercise utilizes an external WiFi card that supports monitor mode, offering hands-on experience with wireless security assessments within an educational framework.

## Command Overview

### Checking and Managing WiFi Interface

- **`iwconfig`**:  
  Lists all wireless interfaces. The correct device is usually not the one labeled `lo` (loopback) or `eth0` (Ethernet). Look for an interface with wireless parameters, which indicates your WiFi card.

- **`sudo airmon-ng check`**:  
  Identifies potential processes that could interfere with the wireless tools. This is a preliminary step before engaging in any wireless network manipulation.

- **`sudo airmon-ng check kill`**:  
  Terminates interfering processes to ensure the wireless tools can operate without issues. This command should be used with caution as it may stop network-related services.

  - To restore network services after the exercise:  
    **`sudo systemctl restart NetworkManager`** restores network services by restarting the NetworkManager, reversing the effects of the `check kill` command.

### Enabling Monitor Mode

- **`sudo airmon-ng start <interface>`**:  
  Enables monitor mode on the specified wireless interface (replace `<interface>` with the actual interface name identified by `iwconfig`). This mode allows the card to capture packets without needing to connect to a network.

### Capturing Packets

- **`sudo airodump-ng <monitor interface>`**:  
  Begins capturing packets on the interface currently in monitor mode, displaying all detectable WiFi networks in the vicinity.

- **`sudo airodump-ng --channel <channel> --bssid <BSSID> --write <filename> <monitor interface>`**:  
  Focuses the packet capture on a specific network by specifying its channel and BSSID. Captured data is saved to the specified file. Replace `<channel>`, `<BSSID>`, `<filename>`, and `<monitor interface>` with the appropriate values.

### Deauthentication Attack

- **`aireplay-ng --deauth <count> -a <BSSID> -c <client MAC> <monitor interface>`**:  
  Sends a specified number of deauthentication packets (`<count>`) to a client (`<client MAC>`) connected to the network (`<BSSID>`), causing disconnection and facilitating the capture of the handshake upon reconnection. Replace `<count>`, `<BSSID>`, `<client MAC>`, and `<monitor interface>` with actual values.

### Cracking the Password

- **`aircrack-ng <capture file> -w <wordlist>`**:  
  Attempts to crack the network password using the specified capture file and a wordlist. Replace `<capture file>` with the name of the file containing the captured handshake and `<wordlist>` with the path to your wordlist file.

## Conclusion

This summary outlines the process for assessing WiFi security through password cracking as part of an educational exercise. Students are reminded to apply these techniques within ethical boundaries and authorized environments only.

