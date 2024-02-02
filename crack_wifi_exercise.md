# WiFi Password Cracking Exercise

## Objective

The objective of this exercise is to provide you with practical experience in cracking WiFi passwords using an external WiFi card that supports monitor mode. This exercise is designed to enhance your understanding of wireless network security and the tools used for ethical hacking within a controlled educational environment.

## Pre-requisites

- External WiFi card that supports monitor mode
- A computer running a Linux distribution (preferably Kali Linux)
- Basic understanding of command line interfaces and networking concepts

## Exercise Overview

You will perform a series of tasks designed to simulate an attack on a wireless network. This includes putting your WiFi card into monitor mode, capturing WiFi traffic, conducting a deauthentication attack, and attempting to crack the network password using a wordlist attack.

### Step 1: Identifying Your Wireless Interface

- **List Wireless Interfaces:**  
  Start by listing all available network interfaces using the command `iwconfig`. Look for interfaces that have wireless information, such as signal strength and link quality. These interfaces are capable of being put into monitor mode.

- **Checking for Interferences:**  
  Before proceeding, ensure that there are no processes that could interfere with the network tools. Use `sudo airmon-ng check` to list potential interfering processes.

- **Stopping Interfering Processes:**  
  If the previous command lists any processes, you can stop them using `sudo airmon-ng check kill`. This will ensure your tools work correctly. Be aware that this may disconnect you from your current network, so ensure you have another means of accessing the internet if needed.

### Step 2: Monitoring and Capturing

- Put your WiFi card into monitor mode to listen to all wireless traffic.
- Identify the target WiFi network you will be attempting to crack. Note its BSSID and the channel it operates on.
- Capture traffic from the target network, specifically aiming to capture the handshake process when a device connects to the network.

### Step 3: Conducting the Attack

- Use a deauthentication attack to disconnect a client from the target network. This will force them to reconnect, allowing you to capture the handshake.
- Ensure you capture the necessary handshake to proceed with the password cracking attempt.

### Step 4: Cracking the Password

- Using the captured handshake, attempt to crack the network password with a wordlist attack.
- Analyze the results to determine if the password was successfully cracked.

## Deliverables

Upon completing the exercise, you are to submit a report that includes:

- The steps you took during each phase of the exercise.
- Any challenges you encountered and how you resolved them.
- The outcome of the password cracking attempt.

## Ethical Consideration

This exercise is conducted within an educational setting for learning purposes only. It is crucial to understand the ethical implications of hacking and to ensure that these skills are used responsibly. You must have explicit permission to attack any network. Unauthorized access to networks and systems is illegal and unethical.
