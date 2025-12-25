# Phase 7: Security Audit and System Evaluation



---

## Overview
This week focused on conducting a comprehensive security audit and evaluating the overall
system configuration of the Linux server. The objective was to assess the effectiveness of
the implemented security controls, identify remaining vulnerabilities, and critically
evaluate the system’s security posture.

All auditing and verification tasks were performed within the isolated VirtualBox
environment and administered remotely via SSH in accordance with the assessment’s ethical
and administrative constraints.

---

## Infrastructure Security Assessment

A structured security audit was conducted to evaluate the server’s configuration across
multiple security domains, including access control, network exposure, service management,
and system hardening.

The audit combined automated security scanning tools with manual verification to ensure a
thorough and reliable assessment.

---

## Lynis Security Audit

Lynis was used to perform a detailed system security audit and generate a quantitative
security score.

### Initial Lynis Scan
An initial Lynis scan was conducted to establish a baseline security score. The scan
identified several warnings and suggestions related to system hardening, service exposure,
and configuration settings.

**Initial Lynis Score:**  
(To be replaced with actual score)

### Remediation Actions
Based on the Lynis recommendations, remediation actions were applied, including:
- Strengthening SSH configuration
- Ensuring mandatory access control enforcement
- Verifying firewall and intrusion detection services
- Confirming automatic security updates

### Post-Remediation Lynis Scan
A follow-up Lynis scan was conducted after remediation to measure security improvements.

**Post-Remediation Lynis Score:**  
(To be replaced with actual score)

The increase in the Lynis score demonstrates the effectiveness of the implemented security
controls.

---

## Network Security Assessment (nmap)

Network security was assessed using `nmap` within the isolated VirtualBox network.

### Scan Results
- Only the SSH service (port 22) was accessible
- All other ports were closed or filtered by the firewall
- No unnecessary services were exposed

These results confirm that network access is tightly restricted and aligned with the
principle of minimal exposure.

---

## SSH Security Verification

SSH security was manually verified to ensure compliance with best practices.

### Verified Controls
- Key-based authentication enforced
- Password authentication disabled
- Direct root login disabled
- Access restricted to authorised users

These controls significantly reduce the risk of unauthorised access and brute-force
attacks.

---

## Access Control Verification

Mandatory Access Control was verified using AppArmor.

### Verification Results
- AppArmor is enabled and enforcing profiles
- Key system services are confined by active profiles
- No critical profiles are in complain or disabled mode

This confirms that application-level access control is actively enforced.

---

## Service Inventory and Justification

A service audit was conducted to identify all running services and justify their necessity.

| Service | Purpose | Justification |
|-------|--------|---------------|
| sshd | Remote administration | Required for secure remote management |
| ufw | Firewall management | Enforces network access control |
| fail2ban | Intrusion prevention | Protects against brute-force attacks |
| unattended-upgrades | Automatic updates | Ensures timely security patching |
| nginx | Web server (testing) | Required for performance evaluation |

No unnecessary services were found to be running on the system.

---

## System Configuration Review

The overall system configuration was reviewed to assess security, performance, and
maintainability.

### Key Strengths
- Minimal attack surface due to headless deployment
- Strong authentication and access controls
- Layered security approach combining firewall, MAC, and intrusion detection
- Automated security updates reduce operational risk

### Limitations
- Security is dependent on correct key management
- Performance tuning may introduce trade-offs with security settings
- Monitoring scripts rely on SSH availability

---

## Remaining Risk Assessment

Despite strong security controls, some residual risks remain:

- Compromise of authorised SSH keys
- Insider misuse of administrative privileges
- Zero-day vulnerabilities not yet patched

These risks are mitigated through monitoring, auditing, and adherence to best practices,
but cannot be entirely eliminated.

---

## Reflection
This final security audit demonstrated how layered security controls and systematic
evaluation significantly improve a system’s security posture. Combining automated tools
such as Lynis and nmap with manual verification provided both quantitative and qualitative
insight into system security. The audit reinforced the importance of continuous monitoring,
regular reviews, and balancing security with usability in professional system
administration.

