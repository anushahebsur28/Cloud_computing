## 5. Proxmox VE Configuration

### Type-1 Hypervisor

The Ubuntu virtual machine is created and configured in Proxmox VE with:

- Ubuntu operating system
- 2 vCPU
- 2 GB RAM
- 20 GB disk

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
