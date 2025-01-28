# Network-Monitoring

### **Zabbix for SNMP Monitoring**
- Monitoring **CPU, memory, bandwidth usage** for all network devices.
- Custom **Zabbix dashboards** for real-time insights.

📄 [View Zabbix Setup](monitoring/zabbix-setup.md)



### **Splunk for Syslog Analysis**
- Collecting logs from **Cisco devices, Windows Server, and Linux VMs**.
- Creating dashboards for **failed login attempts, VPN connections, and network activity**.

📄 [View Splunk Setup](monitoring/splunk-setup.md)

---

# Network Monitoring with Zabbix and SNMP

This repository provides a complete guide to setting up a network monitoring solution using **Zabbix** and **SNMP** to monitor key metrics of network devices like routers, switches, and firewalls. The project includes Zabbix server installation, SNMP configuration for various devices, and creating custom monitoring templates for key network parameters.

## Key Features:
- Zabbix server installation and configuration
- SNMP configuration for network devices
- Custom Zabbix templates for CPU, memory, bandwidth, and uptime monitoring
- Automated scripts for SNMP checks and Zabbix backups

## Installation Guide:
### 1. [Zabbix Server Setup](zabbix-server-setup/zabbix-server-installation.md)
   - Install Zabbix on Ubuntu 20.04
   - Configure the Zabbix server for SNMP monitoring

### 2. [SNMP Configuration](snmp-configuration/snmpd.conf)
   - Configure SNMP on network devices (routers, switches, firewalls) to allow Zabbix to pull monitoring data

### 3. [Zabbix Monitoring Templates](monitoring-templates/zabbix-snmp-template.xml)
   - Import pre-configured templates into Zabbix for monitoring bandwidth, CPU, memory, and uptime

### 4. [Automated Scripts](scripts/)
   - Use `snmp-check.sh` to verify SNMP functionality across devices
   - Use `zabbix-backup.sh` to automate backups of Zabbix configurations

## Screenshots:
- ![Zabbix Dashboard](images/zabbix-dashboard.png)
- ![SNMP Bandwidth Graph](images/snmp-graph.png)
