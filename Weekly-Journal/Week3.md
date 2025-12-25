# 📊 Week 3 – Performance Testing & Monitoring

---

## 1. Introduction

Week 3 focused on evaluating the performance of the Linux server through real-time monitoring and process analysis.  
Rather than configuring new services, the goal was to understand how the operating system behaves under normal conditions and how system resources such as CPU and memory are utilised.

Performance testing is essential for detecting bottlenecks, ensuring stability, and preparing the system for future optimisation and security hardening.

---

## 2. Objectives for This Week

The objectives of Week 3 were:

- Monitor real-time system performance  
- Understand CPU and memory utilisation  
- Observe running processes and background services  
- Analyse overall system behaviour and stability  
- Prepare the environment for future tuning and optimisation tasks  

---

## 3. Performance Monitoring Overview

System monitoring allows administrators to answer critical operational questions:

- Is the system under heavy load?
- Which processes are consuming the most resources?
- Is the server operating within safe limits?

Linux provides several built-in monitoring tools that allow administrators to evaluate system health without installing additional software.

---

## 4. Process Monitoring Using `ps`

### Purpose

The `ps aux` command was used to display a detailed list of running processes along with their CPU and memory usage.

This provides visibility into:
- Active system services
- User processes
- Resource consumption patterns

### Screenshot: Process List Output

![Process List](../Screenshots/Week3/Week3_1_ps_aux.png)

This screenshot shows the list of active processes and demonstrates how system resources are distributed among background services and user applications.

---

## 5. Real-Time System Monitoring Using `top`

### Purpose

The `top` command provides a continuously updating overview of system performance, including:

- CPU usage  
- Memory consumption  
- Load average  
- Number of active and sleeping processes  

### Screenshot: `top` Output

![Top Monitoring](../Screenshots/Week3/Week3_2_top.png)

The output confirms that CPU usage remained low during idle operation and that sufficient memory was available, indicating stable system performance.

---

## 6. Enhanced Monitoring Using `htop`

### Purpose

`htop` was used as an advanced monitoring tool to provide a more visual and user-friendly representation of system performance.

### Advantages of `htop`

- Colour-coded CPU and memory usage  
- Clear visual process hierarchy  
- Improved readability of system metrics  

### Screenshot: `htop` Interface

![Htop Monitoring](../Screenshots/Week3/Week3_3_htop.png)

This screenshot demonstrates the enhanced visibility provided by `htop`, allowing faster identification of system activity and resource distribution.

---

## 7. System Resource Summary

During monitoring, the following observations were recorded:

| Resource | Observation |
|---------|------------|
| CPU | Low utilisation during idle state |
| Memory | Stable usage with sufficient free RAM |
| Processes | Normal background services and user processes |
| System Stability | Maintained throughout monitoring session |

These results indicate that the system is operating efficiently under normal conditions.

---

## 8. Key Learning Outcomes

By completing this week's tasks, the following skills were developed:

- Interpreting performance metrics  
- Identifying resource-heavy processes  
- Monitoring system health in real time  
- Understanding the relationship between system load and stability  
- Using multiple monitoring tools effectively  

---

## 9. Reflection

Week 3 demonstrated the importance of continuous performance monitoring in maintaining a healthy operating system.  
Understanding how CPU, memory, and processes interact provides administrators with the insight required to prevent performance degradation and prepare systems for increased workloads.

These monitoring techniques form a critical foundation for future optimisation, logging, and security configuration tasks.

---

### 🔗 Navigation

[Back to Index](index.md) | [Week 1](Week1.md) | [Week 2](Week2.md) | Week 3 | [Week 4](Week4.md) | [Week 5](Week5.md) | [Week 6](Week6.md) | [Week 7](Week7.md)
