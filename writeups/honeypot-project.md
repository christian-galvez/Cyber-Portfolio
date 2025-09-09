# GitHub Project Write-Up
## Cowrie SSH Honeypot on DigitalOcean
### Overview

This project involved deploying Cowrie
, a medium-interaction SSH honeypot, on a DigitalOcean droplet. The honeypot is designed to log brute-force attempts, shell interaction, and file transfers made by unauthorized users.

## Objectives

- Deploy Cowrie in a secure, isolated environment.
- Capture unauthorized login attempts and attacker activity.
- Learn the pitfalls of configuring a honeypot in a modern Linux environment (Ubuntu 24.04).
- Build real-world troubleshooting experience with Python venvs, system security restrictions, and firewall configuration.

---

## Setup Process

1. Provisioned a DigitalOcean Ubuntu 24.04 droplet.
2. Created a dedicated cowrieuser account (never running Cowrie as root).
3. Cloned the Cowrie repository and set up a Python virtual environment.
4. Resolved PEP 668 issues with Ubuntu’s “externally managed environments” by rebuilding the virtual environment as a non-root user.
5. Installed dependencies via requirements.txt inside the venv.
6. Configured firewall rules and ensured the honeypot port (2222) was exposed externally.
7. Launched Cowrie and verified it was logging unauthorized attempts.

---

## Learning Moments / Troubleshooting

Python packaging restrictions (PEP 668): Ubuntu 24.04 blocks pip installs in system-managed environments. I learned to rebuild the venv properly as a non-root user to avoid externally-managed-environment errors.

Permission issues: Accidentally building the venv as root caused Cowrie to point to /root Python paths, breaking execution. Fixing this reinforced the importance of least-privilege operation.

Firewall configuration: “Connection timed out” errors highlighted the need to open honeypot ports both in UFW and in the cloud provider’s firewall.

Logs as validation: Seeing unauthorized SSH attempts appear in Cowrie’s logs confirmed the deployment was successful and actively interacting with attackers.

## Results

Cowrie is actively recording brute force attempts and commands from unauthorized IPs.

Logs show attacker usernames, password guesses, and attempted commands.

This provides both educational insight into real-world attack behavior and data I can use for further analysis projects.
