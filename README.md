# Ansible IOS Loopback & Static Route Automation

This project demonstrates network automation using Ansible to configure loopback interfaces and static routes across multiple Cisco IOS routers.

The configuration is fully data-driven using `group_vars` and `host_vars`, enabling scalable and reusable deployments.

---

## Project Overview

This playbook performs the following tasks:

- Configures multiple loopback interfaces on each router
- Assigns IP addresses and descriptions dynamically
- Adds static routes (only if defined per device)
- Verifies loopback interfaces configuration
- Verifies static routes in the routing table

---

## 🧱 Project Structure

├── inventory.ini
├── syslog_config.yml
│
├── group_vars/
│ ├── all.yml
│ ├── vault.yml # 🔐 encrypted (not pushed)
│ └── vault.yml.example # sample for users
│
├── host_vars/
│ ├── R1.yml
│ ├── R2.yml
│ └── R3.yml
│
└── README.md


---

## Technologies Used

- Ansible
- Cisco IOS (IOSv)
- YAML (data modeling)
- Ansible Vault (for secrets management)

---

## Secrets Management

Sensitive data such as device credentials are **not stored in plain text**.

This project uses **Ansible Vault** to encrypt secrets.

### How it works

The inventory references a variable:

ansible_password={{ vault_ansible_password }}

The actual password is stored securely in:

group_vars/vault.yml

This file is encrypted using:

ansible-vault encrypt group_vars/vault.yml



---

### Verification Tasks

The playbook validates configuration using:

- `show ip interface brief`
- `show ip route static`

---

## Notes

- All IP addresses and credentials are part of a **simulated lab environment**
- This project is designed for **learning and demonstration purposes**

---

##  Key Design Principles

- **Infrastructure as Code (IaC)**
- **Data-driven automation**
- **Modular configuration using variables**
- **Secure credential management**

---

## Author

**Amina Ahmed**  
Packet Core & IP Network Engineer | Network Automation Enthusiast





