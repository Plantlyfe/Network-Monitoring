# Network Monitoring with Zabbix and SNMP

This repository provides a complete overview to my network monitoring solution using **Zabbix** and **Splunk** to monitor key metrics of network devices. The project involved Linux server configuration and installation, SNMP configuration, and creating custom monitoring templates for key network parameters.

## **Zabbix for SNMP Monitoring**
- Installed Zabbix on Ubuntu Server VM and installed Zabbix agent on both Linux servers & client work stations.
- Configured SNMPv3 on network devices to allow Zabbix to pull monitoring data for secure network monitoring.
- Added hosts & created hostgroups and templates to group devices
- Initially had issues with network device data poplulating in Zabbix. Used Paessler SNMP Tester for troubleshooting. Determined issue was with SNMPv3 configurations which was corrected.
- Monitoring of **CPU, memory, bandwidth usage, uptime etc** for all network devices are now active.
- Created custom **Zabbix dashboards** for real-time insights.

📄 [View Zabbix Setup](monitoring/zabbix-setup.md)

## **Splunk for Syslog Analysis**
- Installed Splunk on Ubuntu Server VM and installed Splunk Universal forwarder on client work stations.
- Enabled HTTPS encryption for Splunk Web interface (HTTP by default)
- Configured Syslog on network devices to send traps to Splunk Server. Also installed Cisco Network Add-ons in Splunk Web Interface.
- Now collecting logs from **Cisco devices, Windows Server, and Linux VMs**.
- Creating dashboards for **Syslog messages, failed login attempts, and network activity, etc**.

![View Splunk Setup](https://github.com/Plantlyfe/Network-Monitoring/blob/main/Splunk%20Syslog%20Dashboard%20-%20Cisco.png)

## Screenshots:
- ![Zabbix Dashboard](images/zabbix-dashboard.png)
- ![SNMP Bandwidth Graph](images/snmp-graph.png)
