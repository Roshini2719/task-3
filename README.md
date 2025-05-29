# 🔒 Vulnerability Assessment Report - Internship Task 3

## 📌 Objective
This project involves conducting a basic vulnerability scan on my personal computer using **Nessus Essentials**, identifying potential security issues, and documenting the findings with suggested remediations.

---

## 🧰 Tools Used

- **Nessus Essentials** – Free vulnerability scanner by Tenable


---

## 📝 Steps Performed

1. Installed and activated **Nessus Essentials**.
2. Set up a local scan targeting `192.168.56.1`.
3. Executed a full system vulnerability scan.
4. Waited ~30–60 minutes for scan completion.
5. Reviewed all vulnerabilities and their CVSS severity.
6. Researched mitigation techniques for high-risk issues.
7. Documented and summarized the most critical vulnerabilities.

---

## 📊 Scan Summary

| Severity    | Count | Example Issues Detected                      |
|-------------|-------|----------------------------------------------|
| **Critical** | 2     | Remote Code Execution, Unpatched Services    |
| **High**     | 4     | SMBv1 Enabled, TLS 1.0/1.1 Support           |
| **Medium**   | 6     | Missing Updates, Insecure Configurations     |
| **Low**      | 8     | Outdated Packages, Informational Issues      |

---

## 🚨 Top Critical Vulnerabilities Identified

### 1. **SMBv1 Protocol Enabled**
- **Severity:** High
- **Description:** Legacy SMBv1 is enabled, which is vulnerable to exploits like EternalBlue.
- **Risk:** Remote attackers can gain unauthorized access or execute code.
- **Fix:** Disable SMBv1 using PowerShell (Windows):
  ```powershell
  Disable-WindowsOptionalFeature -Online -FeatureName "SMB1Protocol"
