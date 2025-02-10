# Wi-Fi Attacks

This document explains various methods attackers may use to exploit Wi-Fi networks.

## Types of Wi-Fi Attacks

### 1. Evil Twin Attack

- **Description**: The attacker sets up a fake Wi-Fi network with a name similar to a legitimate one (e.g., "Home_Internet" becomes "Home_Internnet").
- **How It Works**: Victims are disconnected from their trusted Wi-Fi and connect to the fake one due to frustration or confusion. Once connected, the attacker monitors all their internet traffic.

### 2. Rogue Access Point

- **Description**: A malicious open Wi-Fi network is set up near or within an organization.
- **How It Works**: Devices configured to automatically connect to open networks may join this fake network. The attacker can then intercept and monitor the victim’s communication.

### 3. WPS Attack

- **Description**: Exploits weaknesses in the Wi-Fi Protected Setup (WPS) protocol.
- **How It Works**: The attacker brute-forces the 8-digit WPS PIN during a handshake with the router, gaining access to the network and retrieving the Pre-Shared Key (PSK).

### 4. WPA/WPA2 Cracking

- **Description**: Targets vulnerabilities in the Wi-Fi Protected Access (WPA/WPA2) protocols.
- **How It Works**: Attackers capture the network’s handshake using de-authentication techniques and then brute-force or use dictionary attacks to crack the PSK.
