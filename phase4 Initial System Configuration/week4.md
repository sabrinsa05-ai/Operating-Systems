# Phase 4: Initial System Configuration & Security Implementation

[← Home](index.md) | [Phase 3 3 ←](week3.md) | [Phase 5 →](week5.md)

---

## Overview
This week focused on deploying the Linux server and implementing foundational security
controls. All system administration tasks were performed remotely via SSH from the
workstation, enforcing command-line proficiency and aligning with professional server
administration practices.

The primary objectives were to secure SSH access using key-based authentication, configure
a restrictive firewall, and implement proper user and privilege management.

---

## SSH Key-Based Authentication

SSH was configured to use key-based authentication to prevent password-based attacks and
improve overall system security.

### Configuration Approach
- An SSH key pair was generated on the workstation
- The public key was securely copied to the server
- Password-based authentication was disabled
- Direct root login over SSH was disabled

This ensures that only trusted devices with the correct private key can access the server.

---

## User and Privilege Management

A non-root administrative user was created to enforce the principle of least privilege.

### Implementation Details
- A dedicated administrative user account was created
- The user was granted `sudo` privileges
- Routine administration is performed using this account
- Direct root login was disabled

This approach reduces the risk associated with operating as the root user and improves
auditability of administrative actions.

---

## Firewall Configuration

A host-based firewall was configured to restrict network access to the server.

### Firewall Policy
- Default policy: deny all incoming connections
- Allow SSH access only from the trusted workstation IP
- Allow all outgoing connections

This ensures that only authorised systems can communicate with the server while minimising
the exposed attack surface.

---

## Firewall Ruleset Documentation

The complete firewall ruleset confirms that only SSH traffic from the specified workstation
is permitted. All other inbound traffic is blocked by default.

Firewall status and rules were verified remotely via SSH to ensure correct enforcement.

---

## Configuration File Changes

Security-related configuration files were reviewed and modified as required.

### SSH Configuration
- Before: password authentication enabled, root login permitted
- After: password authentication disabled, key-based authentication enforced, root login
  disabled

Configuration changes were validated by restarting the SSH service and confirming continued
remote access.

---

## SSH Access Evidence

Successful SSH access was demonstrated using the non-root administrative user from the
workstation. All access to the server was performed remotely, with no direct console usage,
in compliance with the assessment constraints.

Screenshots capturing successful SSH connections and command execution will be included
as evidence.

---

## Remote Administration Evidence

All configuration tasks, including user management, firewall configuration, and SSH
hardening, were executed remotely via SSH from the workstation.

This demonstrates command-line proficiency and adherence to the administrative constraints
outlined in the assessment brief.

---

## Reflection
This week reinforced the importance of securing access before deploying additional
services. Implementing key-based SSH authentication, least-privilege user management, and
restrictive firewall rules significantly reduced the server’s attack surface while
maintaining administrative usability.

