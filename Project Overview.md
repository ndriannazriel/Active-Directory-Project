Active Directory is a database that contains objects such as users, groups and etc. In order to use AD, a server must have a service called AD Domain Services(DS). Then, the server must be promoted to a Domain Controller(DC) which will give us the ability to perform authentication using protocol called Kerberos and authorization. 

Each objects in AD will have attributes just like how most how database structures are set up. 

Before I begin, here are the roles of the VMs that will be used for this project. There are a total of 4 VMs that will be used.
1. Windows 10 - Target Machine
2. Kali Linux - Attacker Machine
3. Windows Server 2022 - AD
4. Ubuntu Server - Splunk
## Objectives
1) Create Active Directory
2) Create Users and Groups within AD
3) Use Crowbar/Hydra that matches the users.
4) Detect the attack using Splunk

## Configure Ubuntu Server
![[Pasted image 20250427164248.png]]
After changing the network adapter, statically change the ip address of your Splunk Machine to 192.168.10.10 using the command `sudo nano /etc/netplan/<tab>`.

![[Pasted image 20250427164310.png]]
With the change in place, you can see if it works by pinging the DNS of google.com.

## Installing Splunk on Ubuntu Server

![[Pasted image 20250427164350.png]]
![[Pasted image 20250427164415.png]]
Now every time the ubuntu server is turned on, Splunk services will automatically turn on.
## Connect to Splunk on TM and Windows Server

![[Pasted image 20250427164437.png]]
On the target machine.


![[Pasted image 20250427164454.png]]
On windows server.

## Create Groups and Users in AD
![[Pasted image 20250427164521.png]]
Created users in AD. Once users have been created, now you can enter on the target machine using the credentials created for the users.

## Launching the attack
![[Pasted image 20250427163609.png]]

## Detect Using Splunk
Navigate to Splunk via the Ubuntu Server and observe the things happening. If there is a trace of the attack detected, then the project is a success.
### Troubleshooting

```
sudo apt install freerdp3-x11
sudo ln -s /usr/bin/xfreerdp3 /usr/bin/xfreerdp
which xfreerdp
xfreerdp --version
```

## Conclusion
In this project, I successfully set up an Active Directory environment, created users and groups, and simulated a brute-force attack using Hydra to test account security. Finally, I detected and monitored the attack using Splunk, demonstrating the importance of proactive monitoring and defense in an Active Directory environment which would prove useful as a blue teamer.
