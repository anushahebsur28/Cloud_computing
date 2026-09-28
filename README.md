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

## 3. Hypervisor Comparison

### Type-1 Hypervisor — Proxmox VE

Proxmox VE is used as the Type-1 hypervisor in this experiment.

```text
+------------------------------------------------------+
|             Ubuntu Virtual Machine                   |
|             Sysbench CPU Benchmark                  |
+------------------------------------------------------+
|                 Proxmox VE                          |
|              Type-1 Hypervisor                      |
+------------------------------------------------------+
|              Physical Server Hardware               |
+------------------------------------------------------+
