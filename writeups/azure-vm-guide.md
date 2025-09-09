---
layout: default
title: How to Secure an Azure VM in Under 10 Minutes
---

# 🛡️ How to Secure an Azure VM in Under 10 Minutes

Microsoft Azure provides flexible and powerful infrastructure for hosting virtual machines. But out-of-the-box, your VM may be exposed to various risks. Here’s a quick checklist to lock it down in less than 10 minutes.

---

## ☁️ 1. Choose Secure Defaults During Deployment

- Use a **Resource Group** to organize and isolate resources.
- Enable **SSH key-based authentication** (for Linux) or set a strong RDP password (for Windows).
- Disable unnecessary options (e.g., public IP if not required).

---

## 🔒 2. Restrict Inbound Traffic with Network Security Groups (NSGs)

- Attach an NSG to your VM’s NIC or subnet.
- Allow only essential ports:
  - Linux: TCP 22 (SSH)
  - Windows: TCP 3389 (RDP)
- Restrict inbound traffic to **your IP address**, not “Any.”

---

## 🧱 3. Use Azure Bastion Instead of Public IP Access

- Azure Bastion provides secure RDP/SSH access through the Azure portal.
- Eliminates the need for exposing the VM via a public IP address.

---

## 🦠 4. Enable Microsoft Defender for Cloud

- Turn on **Defender for Servers** to monitor threats, vulnerabilities, and best practices.
- Enable auto-provisioning of endpoint protection.

---

## 🔄 5. Apply Updates and Configure Backup

- Use **Update Management** or manual patching.
- Set up **Azure Backup** to protect the VM and recover from ransomware or failures.

---

## ✅ Summary

Security isn't optional, it's foundational. By securing your Azure VM immediately after deployment, you significantly reduce your attack surface and improve compliance posture.

[⬅️ Back to Writeups](../writeups.md)
