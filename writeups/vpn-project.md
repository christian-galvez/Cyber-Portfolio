---
layout: default
title: WireGuard VPN on DigitalOcean
---
🚀 Project: WireGuard VPN on DigitalOcean
📌 Overview

This project demonstrates the design, deployment, and configuration of a secure WireGuard VPN server hosted on a DigitalOcean droplet. The VPN allows secure remote access from multiple clients (mobile and laptop), ensuring encrypted traffic tunneling and anonymity while browsing the internet.

The project showcases my skills in:
- Linux server administration
- VPN configuration (WireGuard)
- SSH management and troubleshooting
- Network routing, firewall (iptables), and NAT configuration
- Secure client provisioning across devices (iOS + Windows/Linux)
---
🛠️ Tools & Technologies

- DigitalOcean Droplet (Ubuntu 22.04 LTS)
- WireGuard VPN
- iOS WireGuard App
- Windows WireGuard Client
- SSH (OpenSSH)
- iptables for firewall and NAT rules
---
⚙️ Implementation Steps
1. Server Setup

Deployed a fresh Ubuntu server on DigitalOcean.
<img width="979" height="258" alt="image" src="https://github.com/user-attachments/assets/142f5eee-2629-491c-98b6-c0c0bb5c6702" />

Updated system and installed WireGuard:

- sudo apt update && sudo apt upgrade -y
- sudo apt install wireguard -y
<img width="877" height="347" alt="image" src="https://github.com/user-attachments/assets/84fa5a7f-7d0d-4137-baca-7067353a3527" />
---
2. Key Generation

Generated server private/public keys.
Generated unique private/public keys for each client device.

- wg genkey | tee server_private.key | wg pubkey > server_public.key
- wg genkey | tee client_private.key | wg pubkey > client_public.key
<img width="979" height="150" alt="image" src="https://github.com/user-attachments/assets/5c94b78f-abb2-4d3e-bb3a-e962d7b7d1de" />
---
3. Server Configuration (wg0.conf)
<img width="966" height="464" alt="image" src="https://github.com/user-attachments/assets/84023782-1d06-4422-8919-0ca61faf497f" />

Example configuration:

[Interface]
Address = 10.0.0.1/24
ListenPort = 51820
PrivateKey = <server_private_key>
PostUp   = iptables -A FORWARD -i %i -j ACCEPT; iptables -A FORWARD -o %i -j ACCEPT; iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE; iptables -I INPUT 1 -p tcp --dport 22 -j ACCEPT
PostDown = iptables -D FORWARD -i %i -j ACCEPT; iptables -D FORWARD -o %i -j ACCEPT; iptables -t nat -D POSTROUTING -o eth0 -j MASQUERADE; iptables -D INPUT -p tcp --dport 22 -j ACCEPT
---
4. Peer Configuration

- Each client (phone, laptop) was assigned its own configuration file:

Example: client.conf

[Interface]
PrivateKey = <client_private_key>
Address = 10.0.0.2/24
DNS = 1.1.1.1

[Peer]
PublicKey = <server_public_key>
Endpoint = <server_ip>:51820
AllowedIPs = 0.0.0.0/0, ::/0
---
5. Client Deployment

Imported the configuration file into the WireGuard mobile app (via QR code).

Imported the configuration into the WireGuard Windows client via .conf file.
---
6. Validation

Verified handshakes with:

sudo wg
<img width="615" height="239" alt="image" src="https://github.com/user-attachments/assets/4c95e5e4-02a7-4af3-a0e6-819e55e657aa" />
---
7. Hardening
Went a step further by enabling firewall.

sudo ufw allow 22/tcp
sudo ufw allow 51820/udp
sudo ufw enable
---

Confirmed both devices appeared as connected peers.

Tested by browsing to https://whatismyipaddress.com and confirming traffic originated from the VPN server’s IP.
---

🔐 Lessons Learned
- Firewall: Implementing WireGuard VPN highlighted the critical importance of firewall hardening to minimize attack surfaces and enforce strict access controls.
- Routing/NAT: Proper PostUp and PostDown rules are critical for allowing VPN clients to reach the internet.
- Access Control: Each client must have unique keys and AllowedIPs defined, preventing overlaps.
- SSH Lockout Prevention: Adding explicit iptables rules to keep SSH open prevents accidental lockouts when bringing the VPN interface up.
- Cross-Device Deployment: Configuring and testing across iPhone + Windows laptop demonstrated real-world secure access scenarios.
