# Phase 2: Security Planning and Testing Methodology

[← Home](index.md) | [Week 1 ←](week01-planning/index.md) | [Week 3 →](week3.md)

---

## Overview
This week focuses on designing a security baseline and defining a performance testing
methodology for the deployed Linux server. The objective is to plan how the system will
be secured and how its performance will be monitored remotely via SSH before any security
controls are implemented.

---

## Performance Testing Plan

Performance testing will be conducted remotely from the workstation using SSH-based
monitoring tools. This approach reflects real-world server administration practices,
where systems are managed without direct graphical or physical access.

### Remote Monitoring Methodology
The following system metrics will be monitored throughout the coursework:
- CPU usage
- Memory utilisation
- Disk usage and I/O activity
- Network activity and latency
- Process behaviour under load

Monitoring will be carried out using standard Linux command-line tools such as `top`,
`htop`, `free`, `df`, `vmstat`, and network utilities. Measurements will be taken at
baseline (idle system) and during workload execution to enable meaningful comparison.

---

## Security Configuration Checklist

The following checklist defines the planned security baseline for the server:

### SSH Hardening
- Disable password-based authentication
- Enforce key-based SSH authentication
- Restrict SSH access to a trusted workstation
- Disable direct root login over SSH

### Firewall Configuration
- Enable a host-based firewall
- Allow only required ports (SSH on port 22)
- Block all other inbound connections by default

### Mandatory Access Control
- Use AppArmor to confine application behaviour
- Monitor and review enforced AppArmor profiles

### Automatic Updates
- Enable unattended security updates
- Ensure critical security patches are applied automatically

### User Privilege Management
- Create a non-root administrative user
- Use `sudo` for controlled privilege escalation
- Apply the principle of least privilege

### Network Security
- Minimise exposed services
- Monitor open ports and network connections
- Perform network scanning only within the isolated VirtualBox environment

---

## Threat Model

The following security threats were identified as relevant to the server environment:

### Threat 1: Unauthorised SSH Access
**Description:** Attackers may attempt to gain access to the server through brute-force
or credential-guessing attacks.

**Mitigation:**
- Disable password authentication
- Enforce SSH key-based authentication
- Restrict SSH access to known hosts
- Implement intrusion prevention mechanisms

---

### Threat 2: Exposed or Misconfigured Services
**Description:** Unnecessary or misconfigured services may increase the server’s attack
surface.

**Mitigation:**
- Disable unused services
- Apply firewall rules to restrict access
- Regularly review running services

---

### Threat 3: Privilege Escalation
**Description:** A compromised user account could be used to gain elevated privileges on
the system.

**Mitigation:**
- Enforce least-privilege access
- Use `sudo` with auditing
- Disable direct root login
- Monitor system logs for suspicious activity

---

## Reflection
This week highlighted the importance of planning security and performance strategies
before implementing technical changes. Developing a structured security checklist and
threat model clarified how different controls work together to reduce risk, while the
performance testing plan established a consistent methodology for later evaluation.

