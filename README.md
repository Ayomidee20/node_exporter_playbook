# 🛠️ Ansible Playbook for Node Exporter Installation on Linux Servers

This Ansible repository automates the installation and configuration of [Prometheus Node Exporter](https://github.com/prometheus/node_exporter) on Linux servers, including **Amazon Linux**. It simplifies system metrics monitoring setup across multiple servers.

---
---

## ✅ Prerequisites

Before running the playbooks, ensure you have:

- Ansible installed on your control machine
- SSH access to the target Linux servers
- Python installed on the target servers
- Public/private SSH key pair configured

---

## ⚙️ Setup Guide

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/ansible-node-exporter.git
cd ansible-node-exporter
```

### 2. Configure Your Inventory

Edit the inventory.in file with your server IPs and access credentials. Example:

```yml [linux_servers]
192.168.1.10 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/my-key.pem
192.168.1.11 ansible_user=ec2-user ansible_ssh_private_key_file=~/.ssh/my-key.pem
```
### 🚀 Running the Playbooks

For General Linux Servers:
```bash
ansible-playbook -i inventory.in linux_playbook.yml
```
For Amazon Linux Servers:
```
bash ansible-playbook -i inventory.in ansible_linux_playbook.yml
```
### 🔍 What the Playbooks Do

	•	Create a dedicated node_exporter user
	•	Download and extract the latest Node Exporter binary
	•	Move the binary to /usr/local/bin
	•	Set up and enable a systemd service for Node Exporter
	•	Start the service on port 9100
