#  Week 3 – Performance Testing & Monitoring

---

## 1. Introduction

Week 3 focused on evaluating the performance of the Linux server through real-time monitoring and detailed resource analysis.  
Rather than configuring new services, the objective was to understand how the operating system behaves under normal conditions and how system resources such as CPU, memory, and storage are utilised.

Performance testing is essential for detecting bottlenecks, ensuring stability, and preparing the system for future optimisation and security hardening.

---

## 2. Objectives for This Week

The objectives of Week 3 were:

- Monitor real-time system performance  
- Analyse CPU scheduling and memory behaviour  
- Observe running processes and background services  
- Examine disk utilisation and I/O activity  
- Evaluate overall system stability  
- Establish baseline performance metrics  

---

## 3. Performance Monitoring Overview

System monitoring allows administrators to answer critical operational questions:

- Is the system under heavy load?  
- Which processes are consuming the most resources?  
- Is the server operating within safe limits?  

Linux provides powerful built-in tools that enable detailed performance analysis without additional software.

---

## 4. Process Monitoring Using `ps`

### Purpose

The `ps aux` command was used to display a comprehensive list of running processes along with CPU usage, memory consumption, ownership, and execution states.

### Screenshot: Process List Output

![Process List](/Screenshots/Week3/1_week3_ps_aux.png)

This output provides a baseline snapshot of system activity and resource distribution.

---

## 5. Real-Time System Monitoring Using `top`

### Purpose

The `top` utility provides a continuously updating overview of CPU usage, memory consumption, load average, and process scheduling behaviour.

### Screenshot: `top` Output

![Top Monitoring](/Screenshots/Week3/2_week3_top.png)

The display confirms that CPU usage remains low during idle operation and memory usage is stable.

---

## 6. Enhanced Monitoring Using `htop`

### Purpose

`htop` was used as an advanced monitoring tool offering improved visibility, colour-coded metrics, and interactive process control.

### Screenshot: `htop` Interface

![Htop Monitoring](/Screenshots/Week3/3_week3_htop.png)

This interface allows faster identification of system activity and performance trends.

---

## 7. Memory & Disk Usage Analysis

The commands `free -h` and `df -h` were executed to evaluate RAM allocation, swap usage, and disk space consumption.

### Screenshot: Memory & Disk

![Memory & Disk](/Screenshots/Week3/4_week3_free_df.png)

This confirms the system has sufficient memory and storage resources for stable operation.

---

## 8. System Uptime & Load Evaluation

System uptime and load averages were analysed to assess long-term stability and CPU workload trends.

### Screenshot: Uptime & Load

![Uptime & Load](/Screenshots/Week3/5_week3_uptime_load.png)

These values confirm the system is operating efficiently with minimal workload pressure.

---

## 9. Virtual Memory & CPU Scheduling Analysis

The command `vmstat 1 5` was used to inspect context switching, paging behaviour, I/O wait time, and CPU idle activity.

### Screenshot: Virtual Memory & Scheduling

![VMStat](/Screenshots/Week3/6_week3_vmstat.png)

This provides deeper insight into kernel-level scheduling and memory management behaviour.

---

## 10. Disk I/O Performance Analysis

The `iostat` command was used to evaluate disk throughput, latency, and device utilisation.

### Screenshot: Disk I/O Statistics

![IOStat](/Screenshots/Week3/7_week3_iostat.png)


This confirms efficient disk performance and absence of I/O bottlenecks.

---

## 11. Kernel & Hardware Context

System and hardware characteristics were recorded using `uname -a`, `lscpu`, and `lsmem` to link OS behaviour with physical resources.

### Screenshot: Kernel & Hardware Information

![Kernel & Hardware](/Screenshots/Week3/8_week3_kernel_hardware.png)

This establishes the environment in which all performance measurements were observed.

---

## 12. Process Scheduling Policy Inspection

Linux scheduling policies and priorities were analysed using  
`ps -eo pid,ppid,cmd,pri,ni,cls,stat`.

### Screenshot: Scheduling Policies

![Scheduling](/Screenshots/Week3/9_week3_process_scheduling.png)

This confirms balanced scheduling and appropriate priority assignment by the kernel.

---

## 13. Performance Summary

| Resource | Observation |
|---------|------------|
| CPU | Low utilisation during idle operation |
| Memory | Stable usage with sufficient free RAM |
| Disk | Adequate available storage |
| Disk I/O | Efficient throughput with no detected bottlenecks |
| Load Average | Low, indicating healthy system |
| Overall Stability | Maintained throughout testing |

---

## 14. Key Learning Outcomes

- Improved understanding of Linux performance metrics  
- Ability to monitor and interpret live system behaviour  
- Identification of resource-intensive processes  
- Analysis of CPU scheduling and memory management  
- Evaluation of overall system health and stability  

---

## 15. Reflection

This week demonstrated the importance of continuous performance monitoring in maintaining a stable and reliable operating environment.  
The collected metrics provide a strong baseline for future optimisation, security hardening, and capacity planning.

---

### 🔗 Navigation

[Back to Index](index.md) | [Week 1](Week1.md) | [Week 2](Week2.md) | **Week 3** | [Week 4](Week4.md) | [Week 5](Week5.md) | [Week 6](Week6.md) | [Week 7](Week7.md)
