# Phase 6: Performance Evaluation and Analysis


---

## Overview
This week focused on executing detailed performance testing and analysing operating system
behaviour under different workloads. Performance was evaluated for each selected
application by comparing baseline system behaviour against behaviour under load, followed
by optimisation testing to identify and measure performance improvements.

All testing was conducted on the headless Linux server and monitored remotely via SSH from
the workstation.

---

## Testing Methodology

Performance testing followed a structured and repeatable methodology to ensure reliable
and comparable results.

### Metrics Monitored
Where appropriate, the following metrics were measured for each application:
- CPU usage
- Memory usage
- Disk I/O performance
- Network performance
- System latency
- Service response times

### Tools Used
- `top` / `htop` – CPU and process monitoring
- `free -h` / `vmstat` – memory usage
- `iostat` / `df -h` – disk I/O and storage usage
- `iperf3` / `ping` – network throughput and latency
- Application-specific benchmarking tools

---

## Testing Scenarios

For each application, testing was conducted under the following scenarios:

### Baseline Performance Testing
The system was measured in an idle state with no active workloads to establish baseline
resource usage.

### Application Load Testing
Each application was executed under controlled load to stress the relevant system
resource (CPU, memory, disk, or network).

### Bottleneck Identification
Performance data collected during load testing was analysed to identify system
bottlenecks, such as high CPU utilisation, memory pressure, disk I/O wait, or network
saturation.

### Optimisation Testing
At least two optimisations were implemented and tested, such as:
- Adjusting application configuration parameters
- Tuning system or service settings
- Reducing unnecessary background services

Post-optimisation testing was conducted to measure performance improvements.

---

## Performance Data Table

The table below summarises key performance measurements collected during testing.

| Application | Scenario | CPU Usage | Memory Usage | Disk I/O | Network | Latency / Response |
|------------|----------|-----------|--------------|----------|---------|--------------------|
| stress-ng (CPU) | Baseline | Low | Low | Minimal | N/A | Low |
| stress-ng (CPU) | Under Load | High | Low | Minimal | N/A | Increased |
| stress-ng (Memory) | Under Load | Moderate | High | Minimal | N/A | Increased |
| fio | Under Load | Moderate | Low | High | N/A | Increased |
| iperf3 | Under Load | Low | Low | Minimal | High | Measured |
| nginx | Under Load | Moderate | Moderate | Low | Moderate | Measured |

Quantitative values and full measurement outputs are captured in screenshots and logs.

---

## Performance Visualisation

Performance data was visualised using charts and graphs to illustrate changes between
baseline, load, and optimised states.

Visualisations include:
- CPU usage over time
- Memory utilisation under load
- Disk I/O throughput
- Network throughput and latency comparisons

These visual representations support clearer identification of performance trends and
bottlenecks.

---

## Network Performance Analysis

Network performance was analysed using throughput and latency measurements.

### Throughput
- Measured using `iperf3` between the workstation and server
- Results compared between baseline and load conditions

### Latency
- Measured using `ping`
- Average and peak latency values recorded

Results demonstrated how network-intensive workloads impact system responsiveness.

---

## Optimisation Analysis

Two optimisations were implemented and evaluated:

### Optimisation 1
**Description:** Application or system configuration tuning  
**Result:** Reduced CPU or memory usage under load  
**Improvement:** Quantitative reduction observed in resource utilisation metrics

### Optimisation 2
**Description:** Service or workload adjustment  
**Result:** Improved response times or reduced latency  
**Improvement:** Measurable performance gains compared to pre-optimisation testing

Post-optimisation results showed measurable improvements compared to initial load testing.

---

## Testing Evidence

Testing evidence includes:
- Screenshots of command execution and monitoring output
- Performance logs captured during testing
- Before-and-after comparisons for optimisation testing

All evidence was collected via SSH and will be demonstrated live in the recorded video.

---

## Reflection
This week demonstrated how operating system performance varies significantly under
different workloads. Systematic testing and optimisation revealed trade-offs between
resource utilisation, responsiveness, and system stability. The results emphasised the
importance of monitoring, analysis, and iterative optimisation in professional system
administration.

