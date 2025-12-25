  ## Phase 1: System Planning and Distribution Selection

System Architecture

This project uses a dual-system architecture consisting of a headless Linux server
and a separate workstation system. The server is administered remotely via SSH,
enforcing command-line proficiency and reflecting professional system
administration practices.

The workstation is used to initiate SSH connections, manage configuration files,
and perform monitoring tasks, while the server runs without a graphical interface.

## Distribution Selection Justification

Ubuntu Server LTS was selected as the server operating system due to its long-term
support, stability, and extensive documentation. Ubuntu includes built-in security
frameworks such as AppArmor and supports regular security updates, making it well
suited for secure server deployments.

Alternative distributions such as Debian and CentOS were considered. Debian offers
high stability but slower update cycles, while CentOS requires more complex
configuration following recent changes to its release model. Ubuntu Server
provided the best balance between stability, security, and usability.

## Workstation Configuration

The workstation system is a macOS host machine using an SSH client to remotely
administer the server. This approach avoids unnecessary virtual machines while
meeting the requirement for remote command-line administration.

## Network Configuration

The server operates within a virtualised network using NAT or shared networking.
IP addressing is assigned dynamically via DHCP, allowing the workstation to
establish SSH connectivity without exposing the server to external networks.

## System Specifications (CLI Evidence)

System information was collected using standard Linux command-line tools to
document the server environment.

- `uname -a` was used to identify kernel and system architecture.
- `free -h` was used to examine memory availability.
- `df -h` was used to inspect disk usage.
- `ip addr` was used to confirm network configuration.
- `lsb_release -a` was used to identify the Linux distribution and version.

## Reflection

This week focused on planning and system design rather than implementation.
Establishing a clear architecture and justifying technical decisions provided a
strong foundation for later security configuration and performance testing.

