# Phase 5: Advanced Security and Monitoring Infrastructure

[← Home](index.md) | [Week 4 ←](week4.md) | [Week 6 →](week6.md)

---

## Overview
This week focused on implementing advanced security controls and developing monitoring
capabilities for the Linux server. Building on the foundational security configuration
from Week 4, additional mechanisms were deployed to strengthen access control, intrusion
detection, and system visibility.

All configuration and verification tasks were performed remotely via SSH in compliance
with the administrative constraints of the assessment.

---

## Mandatory Access Control (AppArmor)

Mandatory Access Control was implemented using AppArmor to restrict application behaviour
and reduce the potential impact of compromised services.

### Implementation
- AppArmor was enabled and verified on the server
- Existing AppArmor profiles were reviewed
- Enforced profiles were used to confine system services
- AppArmor status and active profiles were documented

### Monitoring and Reporting
AppArmor status and profile enforcement were tracked using command-line tools to verify
which profiles were loaded, enforced, or in complain mode. This provided visibility into
application-level access control and policy enforcement.

---

## Automatic Security Updates

Automatic security updates were configured to ensure that critical patches are applied
without manual intervention.

### Configuration
- Unattended security upgrades were enabled
- The update configuration was verified to apply security patches automatically
- Update logs were reviewed to confirm correct operation

This reduces exposure to known vulnerabilities by ensuring timely patching.

---

## Intrusion Detection with fail2ban

fail2ban was deployed to protect against brute-force attacks and repeated unauthorised
access attempts.

### Configuration
- fail2ban was installed and enabled
- SSH protection was configured using predefined jail rules
- Banning policies were applied to block IPs after repeated failed login attempts

### Verification
fail2ban status was checked remotely to confirm that monitoring and banning rules were
active and functioning as expected.

---

## Security Baseline Verification Script

A security baseline verification script (`security-baseline.sh`) was created to validate
all security configurations implemented in Phases 4 and 5.

### Script Purpose
The script verifies:
- SSH key-based authentication is enabled
- Password authentication is disabled
- Root login over SSH is disabled
- Firewall is active and enforcing rules
- AppArmor is enabled and enforcing profiles
- Automatic updates are configured
- fail2ban is active

### Script Execution
The script runs on the server and is executed remotely via SSH from the workstation.
Clear output is provided to confirm the status of each security control.

All script logic is documented with line-by-line comments explaining its functionality.

---

## Remote Monitoring Script

A remote monitoring script (`monitor-server.sh`) was created on the workstation to collect
performance metrics from the server via SSH.

### Metrics Collected
- CPU usage
- Memory utilisation
- Disk usage
- Network activity
- System uptime

### Operation
The script establishes an SSH connection to the server and executes monitoring commands
remotely. Output is collected and displayed on the workstation to allow performance
analysis without direct server access.

All script components include detailed comments explaining each operation.

---

## Demonstration Evidence

Both scripts were executed live via SSH during testing to demonstrate:
- Correct security verification
- Successful remote monitoring
- Clear and interpretable output

These demonstrations will be included in the recorded video with explanations of each
command and result.

---

## Reflection
This week highlighted the importance of layered security controls and automation in system
administration. Implementing mandatory access control, intrusion detection, and automated
verification scripts significantly improved the server’s security posture while enhancing
operational visibility and maintainability.

