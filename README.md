# Performance Analysis of Type-1 and Type-2 Hypervisors

![Course](https://img.shields.io/badge/Course-Cloud%20Computing%20%2F%20Computer%20Networks-blue)
![Hypervisors](https://img.shields.io/badge/Hypervisors-Proxmox%20VE%20%7C%20VMware%20Workstation-orange)
![Benchmark](https://img.shields.io/badge/Benchmark-Sysbench%20CPU%2020k%20Primes-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## Executive Summary

This project analyzes the CPU performance of a Type-1 Bare-Metal Hypervisor (Proxmox VE) and a Type-2 Hosted Hypervisor (VMware Workstation).

The same Ubuntu virtual machine configuration is used on both hypervisors to perform a fair comparison using the Sysbench CPU benchmark.

## Objective

To compare the CPU performance of Type-1 and Type-2 hypervisors using identical virtual machine configurations and Sysbench CPU benchmarking.

## Hypervisors

### Type-1 Hypervisor
**Proxmox VE**

### Type-2 Hypervisor
**VMware Workstation**

## Virtual Machine Configuration

| Parameter | Proxmox VE | VMware Workstation |
|---|---|---|
| Operating System | Ubuntu | Ubuntu |
| CPU | 2 vCPU | 2 vCPU |
| Memory | 2 GB RAM | 2 GB RAM |
| Disk | 20 GB | 20 GB |
| Benchmark | Sysbench | Sysbench |

## Sysbench Command

```bash
sysbench cpu --cpu-max-prime=20000 run
