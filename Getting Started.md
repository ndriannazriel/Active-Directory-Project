### Hardware Requirements

Windows OS - 16GB Ram
256GB Disk Space

This is the topology that I will be using for the project with all of the VMs in place.

![[Pasted image 20241121200909.png]]

From my first project which only used 2 VMs, for this project I will be using 4 VMs, and we need to install the additional two first before we begin.

### Things you need:

On Kali Machine : 
1) Crowbar/Hydra

On Windows Machine: 
1) Splunk Universal Forwarder
2) Sysmon
3) Atomic Red Team

On Windows Server:
1) Active Directory Domain Services(ADDS)
2) Splunk Universal Forwarder
3) Sysmon

On Ubuntu Server:
1) Splunk

## Windows Server 2022 ISO installation(4.7 GB)

ISO File : https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022

After setting up everything, there is a server manager application which is what will be used to install AD.

## Ubuntu Server for Splunk installation(3.0 GB)

Download : https://ubuntu.com/download/server

