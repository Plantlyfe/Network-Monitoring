# Network Monitoring with Zabbix and Splunk

This repository provides a complete overview to my network monitoring solution using **Zabbix** and **Splunk** to monitor key metrics of network devices. The project involved Linux server configuration and installation, SNMP configuration, software installation on workstations and creating custom monitoring templates for key network parameters.

## **Zabbix for SNMP Monitoring**
<img src="https://github.com/Plantlyfe/Network-Monitoring/blob/main/screenshots/Zabbix_logo-CMYK.png" width="400" height="100">

- Installed Zabbix on Ubuntu Server VM (Zabbix supports SNMP versions v1, v2c, and v3 and SNMP trap collection)
- Installed ZabbixAagent on each individual Linux server & client work station. Zabbix agent is seperate software that fowards network information to a Zabbix Server IP address.
- Within Zabbix server, added hosts (workstations & network devices) & created hostgroups (ex. Linux OS, Windows OS, Hypervisors, etc) and templates to group devices
- Monitoring of **CPU, memory, bandwidth usage, uptime etc** for all network devices & workstations are now active.
- Created custom **Zabbix dashboards** for real-time insights of VMs, Network Devices, Servers, etc

![View Zabbix Setup](https://github.com/Plantlyfe/Network-Monitoring/blob/main/screenshots/Zabbix%20Global%20Overview.png)

### **Zabbix Proxmox Dashboard**
- Created a new User and an API token in Proxmox with the necessary access levels to conduct monitoring. New user created for extra layer of security.
- Copied the resulting Token ID and Secret Key into the newly added Proxmox host macros via {$PVE.TOKEN.ID} and {$PVE.TOKEN.SECRET}.
- At first recived an error stating: *Proxmox VE: API service not available* 
- After some research went back and deleted the Proxmox Host Entry. Re-added the host but this time added the {$PVE.URL.HOST} macro and set the value to the IP address of the Proxmox API host.
- Now able to successfully monitor all invidivudal VMs in Proxmox.


![View Proxmox Dashboard 1](https://github.com/Plantlyfe/Network-Monitoring/blob/main/screenshots/Proxmox%20Dashboard%201.png)
![View Proxmox Dashboard 2](https://github.com/Plantlyfe/Network-Monitoring/blob/main/screenshots/Proxmox%20Dashboard%202.png)


### **Zabbix Network Devices Dashboard**
- Configured SNMPv3 on both Cisco Router and Switches for secure networking monitoring.
- Initially had issues with network device data **_not_** populating in Zabbix. Used Paessler SNMP Tester to troubleshoot. Determined the issue was with the initial SNMPv3 configurations which was then corrected. SNMP Host IP address was configured incorrectly.
- I was unable to configure SNMP on the TP-Link Access Point due to device limitations. As a workaround I setup ping monitor to confirm the status of the Access Point, simply to know if the device is up or down.

![View Network Devices Dashboard](https://github.com/Plantlyfe/Network-Monitoring/blob/main/screenshots/Network%20Devices%20Dashboard.png)


## **Splunk for Syslog Analysis**
<img src="https://github.com/Plantlyfe/Network-Monitoring/blob/main/screenshots/logo-splunk-acc-rgb-k.png" width="307.18" height="121.93">

- Installed Splunk on Ubuntu Server VM and installed Splunk Universal forwarder on each individual client work stations.
- Enabled HTTPS encryption for Splunk Web interface (HTTP by default)
- Configured Syslog on network devices to send traps to Splunk Server. Also installed Cisco Network Add-ons in Splunk Web Interface.
- Initially Splunk Server did not collect any logs. During troubleshooting steps, verifed configuration on devices were accurate. Determined that splunk universal forwarder was not  installed correctly on splunk sever. Issue resolved after reinstalling universal forwarder correctly.
- Now collecting logs from **Cisco devices, Windows Server, and Linux VMs**.
- Creating dashboards for **Syslog messages, failed login attempts, and network activity, etc**.

![View Splunk Setup](https://github.com/Plantlyfe/Network-Monitoring/blob/main/screenshots/Splunk%20Syslog%20Dashboard%20-%20Cisco.png)
