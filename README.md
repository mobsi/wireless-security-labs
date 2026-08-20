# Wireless Network Security Labs

Hands-on wireless security work carried out in my home lab, using Kali Linux and a dedicated wireless test environment. All work was performed against my own equipment and isolated test networks — no third-party or production networks were involved.

## Skills Demonstrated

- Kali Linux administration and tooling (aircrack-ng suite, airgeddon, Wireshark)
- 802.11 wireless protocol analysis (beacon frames, authentication/association handshakes, DHCP, deauthentication)
- Wireless network reconnaissance and monitor-mode packet capture
- Rogue access point (Evil Twin) attack methodology and mitigation awareness
- WPA/WPA2 handshake capture and offline password auditing
- Practical understanding of why these attacks work, to inform defensive controls (client isolation, WIDS/WIPS, certificate-based EAP, user awareness training)

## 1. Wireless Traffic Analysis (Wireshark)

Captured and analysed live 802.11 traffic to identify:
- SSIDs, BSSIDs, and beacon frame intervals
- Source/destination/transmitter/receiver MAC addressing across management, control, and data frames
- The full connection lifecycle: probe request/response → authentication → association → DHCP → TCP handshake (SYN/SYN-ACK) → session teardown (deauthentication, DHCP release)
- Supported and extended data rates advertised by an access point

This is standard packet-level analysis used in troubleshooting connectivity issues and investigating suspicious wireless activity.

## 2. Evil Twin Attack Simulation

Simulated a rogue access point (Evil Twin) attack in an isolated lab environment to understand how attackers impersonate a legitimate SSID to intercept credentials via a fake captive portal, and how deauthentication frames are used to force client reconnection to the rogue AP.

**Why this matters professionally:** understanding this attack from the offensive side directly informs the defensive side — recognising why enterprise networks should enforce certificate-based authentication (EAP-TLS) rather than open or PSK-based Wi-Fi, why WIDS/WIPS rogue-AP detection matters, and why user training on verifying network authenticity is a real control, not a formality.

## 3. WPA/WPA2 Security Auditing

Conducted a WPA2 handshake capture and offline password audit against my own test network, to understand the practical weaknesses of PSK-based Wi-Fi security and why dictionary-resistant passphrases and WPA3/SAE matter in a production environment.

*(Methodology described at a summary level rather than as a step-by-step guide — happy to walk through the technical detail directly in an interview.)*

## Tools Used

`Kali Linux` · `aircrack-ng` · `airgeddon` · `Wireshark` · `airodump-ng`
