# Week 2 – Security Planning and Testing Methodology

[← Home](index.md) | [Week 1 ←](week01-planning/index.md) | [Week 3 →](week3.md)

---

## Overview
This week focused on designing a security baseline for the Linux server and defining a
methodology for performance testing. The aim was to identify potential security threats,
plan appropriate mitigations, and establish a structured approach for monitoring system
performance remotely via SSH.

---

## Performance Testing Plan

Performance testing will be conducted remotely from the workstation using SSH-based
monitoring tools. This approach reflects real-world server administration practices where
systems are managed without direct physical or graphical access.

### Monitoring Methodology
The following metrics will be monitored throughout the coursework:
- CPU usage
- Memory utilisation
- Disk usage and I/O activity
- Network activity and latency
- Process behaviour under load

Monitoring will be performed using standard Linux command-line tools such as `top`,
`htop`, `vmstat`, `free`, `df`, and network utilities. Measurements will be captured at
baseline and during application workload testing to allow comparison.

---

## Security Configuration Checklist

The following checklist defines the planned security baseline for the server:

- **SSH Hardening**
  - Disable password-based authentication
  - Enforce key-based authentication
  - Restrict SSH access to a known workstation

- **Firewall Configuration**
  - Enable firewall (UFW)
  - Allow only required ports (SSH on port 22)
  - Restrict access by source IP where possible

- **Mandatory Access Control**
  - Use AppArmor to enforce application confinement
  - Monitor and review access control profiles

- **Automatic Updates**
  - Enable unattended security updates
  - Ensure critical patches are applied automatically

- **User and Privilege Management**
  - Create a non-root administrative user
  - Use `sudo` for privilege escalation
  - Disable direct root login over SSH

- **Network Security**
  - Minimise exposed services
  - Monitor open ports and active connections

This checklist will be verified later using automated scripts and security auditing tools.

---

## Threat Model

The following threats were identified as relevant to the deployed server:

### Threat 1: Unauthorised SSH Access
**Description:** Attackers may attempt to gain access using brute-force or credential
guessing attacks.

**Mitigation:**
- Disable password authentication
- Use SSH key-based authentication
- Implement `fail2ban` to block repeated failed login attempts

---

### Threat 2: Misconfigured or Exposed Services
**Description:** Unnecessary services may increase the attack surface of the server.

**Mitigation:**
- Review and disable unused services
- Use firewall rules to restrict network access
- Perform regular service audits

---

### Threat 3: Privilege Escalation
**Description:** A compromised user account could be used to gain elevated privileges.

**Mitigation:**
- Enforce least-privilege principles
- Use `sudo` with auditing
- Disable root SSH login
- Monitor logs for suspicious activity

---

## Testing and Validation Strategy

Security controls will be validated through:
- Manual inspection of configuration files
- Command-line verification of firewall and SSH settings
- Automated security auditing using tools such as Lynis
- Network scanning within the isolated VirtualBox environment

Performance testing will follow a consistent structure:
1. Baseline measurement
2. Application load testing
3. Bottleneck identification
4. Optimisation and re-testing

---

## Reflection

This week highlighted the importance of planning security and performance strategies
before implementing technical changes. Developing a structured checklist and threat
model clarified how different security controls work together to reduce risk. It also
reinforced the need to balance security with system usability and performance, which
will be explored further in later weeks.

