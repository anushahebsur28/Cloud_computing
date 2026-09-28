# Performance Analysis of Type-1 and Type-2 Hypervisors

![Course](https://img.shields.io/badge/Course-Cloud%20Computing%20%2F%20Computer%20Networks-blue)
![Hypervisors](https://img.shields.io/badge/Hypervisors-Proxmox%20VE%20%7C%20VMware%20Workstation-orange)
![Benchmark](https://img.shields.io/badge/Benchmark-Sysbench%20CPU%2020k%20Primes-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 1. Objective

To perform a performance analysis of Type-1 and Type-2 hypervisors by creating identically configured Ubuntu virtual machines on Proxmox VE and VMware Workstation and comparing their CPU performance using Sysbench.

---

## 2. Hypervisors Used

### Type-1 Hypervisor

**Proxmox VE**

Proxmox VE is used as the Type-1 bare-metal hypervisor.

### Type-2 Hypervisor

**VMware Workstation**

VMware Workstation is used as the Type-2 hosted hypervisor.

---

## 3. Software and Tools Required

- Proxmox VE
- VMware Workstation
- Ubuntu 22.04 or later
- Sysbench
- Git
- GitHub
- Google Chrome / Mozilla Firefox

---

## 4. Standard Virtual Machine Configuration

The same virtual machine configuration is used on both hypervisors to ensure a fair performance comparison.

| Resource | Configuration |
|---|---|
| Guest Operating System | Ubuntu |
| CPU | 2 vCPU |
| Memory | 2 GB RAM |
| Disk | 20 GB |
| Benchmark Tool | Sysbench |

---

## 5. Proxmox VE Configuration

### Type-1 Hypervisor

The Ubuntu virtual machine is created and configured in Proxmox VE with:

- Ubuntu operating system
- 2 vCPU
- 2 GB RAM
- 20 GB disk

### Proxmox Screenshots

#### 5.1 Proxmox VE Dashboard

![Proxmox Dashboard](screenshots/type1-proxmox/01-proxmox-dashboard.png)

#### 5.2 Proxmox Virtual Machine Configuration

![Proxmox VM Configuration](screenshots/type1-proxmox/02-proxmox-vm-configuration.png)

#### 5.3 Proxmox Virtual Machine Running

![Proxmox VM Running](screenshots/type1-proxmox/03-proxmox-vm-running.png)

#### 5.4 Ubuntu Running in Proxmox Console

![Ubuntu Proxmox Console](screenshots/type1-proxmox/04-proxmox-ubuntu-console.png)

#### 5.5 Proxmox CPU and Memory Configuration

The following commands are executed inside the Ubuntu virtual machine:

```bash
lscpu
free -h
