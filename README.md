# Network Monitoring with Zabbix and Splunk

This repository provides a complete overview to my network monitoring solution using **Zabbix** and **Splunk** to monitor key metrics of network devices. The project involved Linux server configuration and installation, SNMP configuration, software installation on workstations and creating custom monitoring templates for key network parameters.

## **Zabbix for SNMP Monitoring**
- Installed Zabbix on Ubuntu Server VM and installed Zabbix agent on both Linux servers & client work stations.
- Configured SNMPv3 on network devices to allow Zabbix to pull monitoring data for secure network monitoring.
- Added hosts & created hostgroups and templates to group devices
- Initially had issues with network device data poplulating in Zabbix. Used Paessler SNMP Tester for troubleshooting. Determined issue was with SNMPv3 configurations which was corrected.
- Monitoring of **CPU, memory, bandwidth usage, uptime etc** for all network devices are now active.
- Created custom **Zabbix dashboards** for real-time insights of VMs, Network Devices, Servers, etc

![View Zabbix Setup](https://github.com/Plantlyfe/Network-Monitoring/blob/main/Zabbix%20Global%20Overview.png)

### **Zabbix Proxmox Dashboard**
- Created a new User and an API token in Proxmox with the necessary access levels to conduct monitoring. New user created for extra layer of security.
- Copied the resulting Token ID and Secret Key into the newly added Proxmox host macros via {$PVE.TOKEN.ID} and {$PVE.TOKEN.SECRET}.
- At first recived an error stating: *Proxmox VE: API service not available* 
- After some research went back and deleted the Proxmox Host Entry. Re-added the host but this time added the {$PVE.URL.HOST} macro and set the value to the IP address of the Proxmox API host.
- Now able to successfully monitor all invidivudal VMs in Proxmox.
- Monitoring is dynamic and automatically adds any new VMs created to the dashboard


![View Proxmox Dashboard 1](https://github.com/Plantlyfe/Network-Monitoring/blob/main/Proxmox%20Dashboard%201.png)
![View Proxmox Dashboard 2](https://github.com/Plantlyfe/Network-Monitoring/blob/main/Proxmox%20Dashboard%202.png)


### **Zabbix Network Devices Dashboard**

## **Splunk for Syslog Analysis**
- Installed Splunk on Ubuntu Server VM and installed Splunk Universal forwarder on client work stations.
- Enabled HTTPS encryption for Splunk Web interface (HTTP by default)
- Configured Syslog on network devices to send traps to Splunk Server. Also installed Cisco Network Add-ons in Splunk Web Interface.
- Now collecting logs from **Cisco devices, Windows Server, and Linux VMs**.
- Creating dashboards for **Syslog messages, failed login attempts, and network activity, etc**.

![View Splunk Setup](https://github.com/Plantlyfe/Network-Monitoring/blob/main/Splunk%20Syslog%20Dashboard%20-%20Cisco.png)
