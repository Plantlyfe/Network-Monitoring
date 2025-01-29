# Network Monitoring with Zabbix and SNMP

This repository provides a complete overview to my network monitoring solution using **Zabbix** and **Splunk** to monitor key metrics of network devices. The project involved Linux server configuration and installation, SNMP configuration, and creating custom monitoring templates for key network parameters.

### **Zabbix for SNMP Monitoring**
- Zabbix server configuration and agent installation
- Configure SNMPv3 on network devices to allow Zabbix to pull monitoring data for secure network monitoring
- Paessler SNMP Tester for troubleshooting
- Monitoring **CPU, memory, bandwidth usage, uptime etc** for all network devices.
- Custom **Zabbix dashboards** for real-time insights.

📄 [View Zabbix Setup](monitoring/zabbix-setup.md)


### **Splunk for Syslog Analysis**
- Collecting logs from **Cisco devices, Windows Server, and Linux VMs**.
- Creating dashboards for **Syslog messages, failed login attempts, and network activity, etc**.

![View Splunk Setup](https://github.com/Plantlyfe/Network-Monitoring/blob/main/Splunk%20Syslog%20Dashboard%20-%20Cisco.png)


## Screenshots:
- ![Zabbix Dashboard](images/zabbix-dashboard.png)
- ![SNMP Bandwidth Graph](images/snmp-graph.png)
