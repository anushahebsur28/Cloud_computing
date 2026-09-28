# Performance Analysis of Type-1 and Type-2 Hypervisors

[![Course](https://img.shields.io/badge/Course-Cloud%20Computing-blue.svg)](#)
[![Type-1](https://img.shields.io/badge/Type--1-Proxmox%20VE-orange.svg)](#)
[![Type-2](https://img.shields.io/badge/Type--2-VMware%20Workstation-blue.svg)](#)
[![Benchmark](https://img.shields.io/badge/Benchmark-Sysbench-green.svg)](#)

---

## Executive Summary

This project performs a performance analysis of a Type-1 Hypervisor (Proxmox VE) and a Type-2 Hypervisor (VMware Workstation).

Identically configured Ubuntu virtual machines are used on both hypervisors to ensure a fair performance comparison. The CPU performance is evaluated using the Sysbench CPU benchmark with a maximum prime number value of 20,000.

The benchmark results are compared using:

- Total Execution Time
- Total Events
- Events per Second
- Average Latency

---
### Key Finding

> **Proxmox VE (Type-1 Hypervisor) achieved 1,716.69 Events/sec compared to VMware Workstation's 1,364.78 Events/sec — demonstrating a +25.79% throughput advantage and a 20.55% reduction in average latency.**

---

## 1. Project Objective

The objective of this experiment is to compare the CPU performance of Type-1 and Type-2 hypervisors using identical Ubuntu virtual machines.

The experiment involves:

1. Creating an Ubuntu virtual machine on Proxmox VE.
2. Creating an Ubuntu virtual machine on VMware Workstation.
3. Configuring both virtual machines with identical resources.
4. Installing Sysbench.
5. Running the same CPU benchmark on both virtual machines.
6. Recording and comparing the benchmark results.

---

## 2. Requirements

### Hardware and Software Requirements

| Component | Requirement |
|---|---|
| Type-1 Hypervisor | Proxmox VE |
| Type-2 Hypervisor | VMware Workstation |
| Guest Operating System | Ubuntu 22.04 or later |
| Web Browser | Google Chrome / Mozilla Firefox |
| Performance Testing Tool | Sysbench |
| Version Control System | Git |
| Remote Repository Platform | GitHub |

### VMware Workstation Requirements

- VMware Workstation
- Ubuntu ISO image
- Minimum 20 GB free disk space
- Minimum 4 GB available RAM
- Internet connectivity
- Git installed

---
## 2. Hypervisor Architectural Comparison

### Type-1 Hypervisor — Proxmox VE (Bare-Metal Architecture)

Proxmox VE runs directly on the bare-metal physical host hardware. The Linux kernel integrated with KVM (Kernel-based Virtual Machine) acts as the hypervisor. Guest operating system instructions execute directly on hardware CPU VT-x/AMD-V extensions without passing through an intermediate desktop operating system.

```mermaid
graph TD
    subgraph Physical_Hardware["Physical Hardware (CPU, Memory, Storage, NIC)"]
    end
    
    subgraph Type1_Layer["Proxmox VE Hypervisor (Bare-Metal OS & KVM Kernel)"]
    end
    
    subgraph Guest_VM1["Ubuntu 24.04 Virtual Machine (CC-Experiment1-type1)"]
        Sysbench1["Sysbench CPU Benchmark"]
    end
    
    Physical_Hardware --> Type1_Layer
    Type1_Layer --> Guest_VM1
```

```
+-------------------------------------------------------------------+
|               Ubuntu Virtual Machine (Type-1 Guest)               |
+-------------------------------------------------------------------+
|               Proxmox VE Hypervisor (Linux Kernel / KVM)          |
+-------------------------------------------------------------------+
|                 Physical Server Hardware (Bare Metal)             |
+-------------------------------------------------------------------+
```

---

### Type-2 Hypervisor — VMware Workstation (Hosted Architecture)

VMware Workstation runs as an application process on top of a host operating system (Windows 11/10). CPU requests from the guest VM must navigate through the VMware VMM engine, translate through host OS system calls, and be scheduled by the Windows NT kernel scheduler before reaching physical hardware.

```mermaid
graph TD
    subgraph Physical_Hardware2["Physical Hardware (CPU, Memory, Storage, NIC)"]
    end

    subgraph Host_OS["Host Operating System (Windows 11 / Windows NT Kernel)"]
    end
    
    subgraph Type2_Layer["VMware Workstation (Type-2 Hypervisor Application)"]
    end
    
    subgraph Guest_VM2["Ubuntu Virtual Machine (CC-Experiment1-Type2)"]
        Sysbench2["Sysbench CPU Benchmark"]
    end
    
    Physical_Hardware2 --> Host_OS
    Host_OS --> Type2_Layer
    Type2_Layer --> Guest_VM2
```

```
+-------------------------------------------------------------------+
|               Ubuntu Virtual Machine (Type-2 Guest)               |
+-------------------------------------------------------------------+
|               VMware Workstation (Virtual Machine Monitor)        |
+-------------------------------------------------------------------+
|               Host Operating System (Windows 11 / 10)             |
+-------------------------------------------------------------------+
|                        Physical PC Hardware                       |
+-------------------------------------------------------------------+
```

---
   |
+------------------------------------------------------+
