# Week 3 – Performance Testing & Monitoring (Phase 3)

---

## 1. Introduction

Week 3 focused on selecting representative workloads and evaluating the performance of the Linux server through controlled testing and real-time monitoring.  
The objective was to establish a performance baseline that supports future optimisation and security hardening decisions.

---

## 2. Objectives for This Week

The objectives of Week 3 were:

- Select applications representing different workload types  
- Install and execute testing tools remotely via SSH  
- Define expected resource behaviour  
- Monitor CPU, memory, disk, and network performance  
- Establish baseline performance metrics  

---

## 3. Application Selection Matrix

| Workload Type     | Application / Tool | Justification |
|------------------|------------------|-------------|
| CPU-intensive    | stress-ng        | Simulates heavy computational load |
| RAM-intensive    | stress-ng (vm)   | Generates sustained memory pressure |
| Disk I/O-intensive | fio           | Measures storage throughput and latency |
| Network-intensive | iperf3          | Simulates high network traffic |
| Server workload  | openssh-server   | Represents continuous real-world server service |

---

## 4. Installation Documentation (SSH-Based)

All applications were installed remotely via SSH.

```bash
sudo apt update
sudo apt install -y htop sysstat stress-ng fio iperf3
sudo systemctl enable --now sysstat
5. Expected Resource Profiles
Application	CPU Usage	Memory Usage	Disk I/O	Network Activity
stress-ng (CPU)	High	Low	Low	None
stress-ng (VM)	Medium	High	Low	None
fio	Medium	Low	High	None
iperf3	Low–Medium	Low	None	High
ssh service	Low	Low	Low	Low
6. Monitoring Strategy
Resource	Monitoring Tools	Purpose
CPU	top, htop, uptime	Observe load and scheduling
Memory	free -h, vmstat	Analyse memory pressure
Disk	df -h, iostat	Measure storage behaviour
Network	iperf3	Measure throughput
Processes	ps aux	Identify resource-heavy tasks
7. Process Monitoring Using ps

8. Real-Time System Monitoring

9. Memory & Disk Usage

10. Uptime & Load Evaluation

11. Virtual Memory & CPU Scheduling

12. Disk I/O Performance

13. Kernel & Hardware Context

14. Process Scheduling Policies

15. Performance Summary
Resource	Observation
CPU	Stable with low idle load
Memory	Adequate available memory
Disk	Sufficient storage and throughput
Disk I/O	No detected bottlenecks
Network	Stable during tests
Overall Stability	Maintained throughout testing
16. Reflection

This phase established a structured performance testing methodology by combining workload selection, controlled testing, and comprehensive monitoring.
The collected results form a reliable baseline for future system optimisation and security evaluation.
