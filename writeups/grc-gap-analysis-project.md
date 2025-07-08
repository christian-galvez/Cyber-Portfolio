---
layout: default
title: Mock NIST CSF Gap Analysis Project
---

# 🧾 Mock NIST Cybersecurity Framework Gap Analysis

This project demonstrates a mock gap analysis based on the NIST Cybersecurity Framework (CSF). It simulates a small business evaluating its current cybersecurity posture.

---

## 🏢 Organization Profile

**Name:** ACME Widgets Inc.  
**Size:** 45 employees  
**Industry:** Manufacturing  
**Infrastructure:** Cloud-based ERP (Dynamics 365), Office 365, on-premises file server

---

## 🔐 Framework Used

**NIST Cybersecurity Framework (CSF)**  
Core Functions: Identify, Protect, Detect, Respond, Recover

---

## ✅ Objectives

- Map current practices to NIST CSF categories  
- Identify control gaps  
- Recommend actionable improvements

---

## 📊 Gap Table

| NIST Function | Category             | Example Subcategory                  | Status          | Notes                                      |
|---------------|----------------------|--------------------------------------|------------------|--------------------------------------------|
| Identify      | Asset Management     | ID.AM-1: Inventory of physical devices | ✅ Implemented   | Manual asset inventory via spreadsheet     |
| Protect       | Access Control       | PR.AC-1: Identities managed          | ⚠️ Partial        | No MFA on VPN                              |
| Detect        | Anomalies & Events   | DE.AE-1: Baseline of network operations | ❌ Not Implemented | No SIEM/log monitoring                     |
| Respond       | Response Planning    | RS.RP-1: Response plan established   | ✅ Yes           | Documented IR plan (drafted this year)     |
| Recover       | Recovery Planning    | RC.RP-1: Recovery plan in place      | ⚠️ Partial        | Backup tested monthly, no disaster test    |

---

## 🛠️ Tools Used

- Microsoft Excel (gap table)  
- NIST CSF Excel mapping tool  
- Internal IT interviews (simulated)

---

## 📌 Recommendations

- Deploy MFA for all remote access and admin accounts  
- Implement centralized log collection (e.g., Azure Sentinel, Splunk Free)  
- Test backup + recovery procedures at least quarterly  
- Develop and train staff on an incident response plan

---

## 🧠 What I Learned

This project gave me hands-on experience interpreting a cybersecurity framework and applying it to a real-world-like scenario. I gained familiarity with security control mapping, identifying weaknesses, and writing risk-based recommendations.

[⬅️ Back to Writeups](../writeups.md)
