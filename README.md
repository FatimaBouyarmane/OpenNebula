# OpenNebula with VMware vCenter Integration 🚀

<div align="center">
  
[![OpenNebula](https://img.shields.io/badge/OpenNebula-6.4-blue.svg)](https://opennebula.io/)
[![VMware](https://img.shields.io/badge/VMware-vCenter-green.svg)](https://www.vmware.com/)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

*A powerful hybrid cloud management platform combining OpenNebula's orchestration capabilities with VMware vCenter's robust virtualization infrastructure.*

</div>

## 📑 Table of Contents
- [Overview](#-overview)
- [Objectives](#-objectives)
- [Requirements](#-requirements)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Conclusion](#-conclusion)

## 🌟 Overview

This project implements the integration of OpenNebula with VMware vCenter, creating a unified cloud management solution. It provides detailed guidance for setup, configuration, and maintenance of the hybrid cloud environment.

## 🎯 Objectives

- Deploy OpenNebula on Linux-based virtual machine
- Configure seamless integration with VMware vCenter
- Implement automated resource management
- Optimize performance and resource utilization
- Provide comprehensive documentation for maintenance

## 📋 Requirements

### VMware vCenter
- Administrator access rights
- Access to vCenter interface
- Proper network configuration

### Linux Virtual Machine
- Ubuntu/CentOS (recommended)
- Network connectivity to vCenter
- Basic system packages
- OpenNebula API access

### Network Requirements
- Internal network access
- Internet connectivity
- Proper firewall configuration

## 🛠️ Installation

### Step 1: Deploy OVF Model
  Upload and configure OVF template in vCenter
  Set deployment parameters:
  Name: opennebula-vcenter
  Location: preferred_cluster
  Network: management_network

### Step 2: Initial VM Configuration

Update system packages

    sudo apt update && sudo apt upgrade -y
    Install required packages
    sudo apt install -y wget curl openssh-server


### Step 3: Install OpenNebula

Add OpenNebula repository

    sudo wget -q -O- https://downloads.opennebula.org/repo/repo.key | sudo apt-key add -
    sudo echo "deb https://downloads.opennebula.org/repo/6.4/Ubuntu/20.04 stable opennebula" > /etc/apt/sources.list.d/opennebula.list
    Install OpenNebula packages
    sudo apt update
    sudo apt install -y opennebula opennebula-sunstone



## ⚙️ Configuration

### Step 1: Start Services
    Start OpenNebula services
    sudo systemctl start opennebula
    sudo systemctl start opennebula-sunstone
    Verify services status
    sudo systemctl status opennebula
    sudo systemctl status opennebula-sunstone


### Step 2: vCenter Plugin Setup
Download vCenter plugin

    wget -P /tmp https://github.com/OpenNebula/addon-vcenter/releases/download/v5.12.0/vcenter.v5.12.0.tar.gz
    Install plugin
    sudo tar -xvf /tmp/vcenter.v5.12.0.tar.gz -C /
    Configure vCenter connection
    sudo nano /etc/one/vcenter_driver.default


    Restart OpenNebula
    sudo systemctl restart opennebula



## 🎉 Conclusion

This integration provides:
- Centralized cloud resource management
- Automated workflow capabilities
- Scalable cloud infrastructure
- Enhanced performance monitoring

## 📚 Documentation

- [OpenNebula Docs](https://docs.opennebula.io)
- [VMware vCenter Docs](https://docs.vmware.com/en/VMware-vSphere/index.html)

---

<div align="center">
  Made with ❤️ for cloud computing enthusiasts
</div>
