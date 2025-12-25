# Phase 3: Application Selection for Performance Testing


---

## Overview
This week focuses on selecting representative applications to evaluate operating system
performance under different workload types. Each application was chosen to stress a
specific system resource while remaining suitable for deployment on a headless Linux
server administered remotely via SSH.

---

## Application Selection Matrix

The following applications were selected to represent a range of workload types required
for performance evaluation.

| Workload Type | Application | Justification |
|--------------|------------|---------------|
| CPU-intensive | `stress-ng` | Generates controlled CPU load, allowing analysis of scheduling and CPU utilisation |
| RAM-intensive | `stress-ng` (vm workers) | Allocates and consumes memory to observe memory management and paging behaviour |
| I/O-intensive | `fio` | Industry-standard tool for benchmarking disk read/write performance |
| Network-intensive | `iperf3` | Measures network throughput and latency between systems |
| Server application | `nginx` | Lightweight and widely used production web server suitable for headless deployment |

---

## Installation Documentation

All applications will be installed on the server remotely via SSH using the system package
manager. The following commands document the planned installation process.

### stress-ng
```bash
sudo apt update
sudo apt install stress-ng
sudo apt install fio
sudo apt install iperf3
sudo apt install nginx

