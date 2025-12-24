  ## Phase 1: System Planning and Distribution Selection

## System Architecture
![Architecture Diagram](images/week1/architecture.png)

This project uses a dual-system architecture consisting of a headless Linux server
administered remotely via SSH from a workstation.

## Server Distribution Selection
Ubuntu Server 22.04 LTS was selected due to its long-term support, stability, and
built-in AppArmor security framework.

## Workstation Configuration
The workstation is the host macOS system using an SSH client to access the server.

## Network Configuration
The VirtualBox network uses NAT for initial connectivity with IP addressing assigned
via DHCP.

## System Specifications (CLI Evidence)

### uname -a
![uname output](images/week1/uname-output.png)

The uname command displays kernel and system architecture information.

### free -h
![free output](images/week1/free-output.png)

This command shows memory availability in human-readable format.

## Reflection
This week focused on planning and system setup. Learning to deploy a headless server
reinforced the importance of command-line proficiency.
