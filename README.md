<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this project, I observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1: Create a resource group in the Azure Portal.
- Step 2: Create a Windows 10 virtual machine within the resource group.
- Step 3: Create a virtual network for the virtual machine. When you create a virtual network, it will automatically create a network security group, network interface, and hard drive.
- Step 4: Create a Linux (Ubuntu_ virtual machine within the resource group and virtual network.
- Step 5: Install wireshark a protocol analyzer

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open the Windows 10 and linux virtual machines via remote desktop connection by gabbing their public ip addresses through the Azure portal, making sure that the virtual machines are on the same virtual network.   
  
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install wireshark https://www.wireshark.org/ in the Windows 10 virtual machine.

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filter traffic by ICMP and attempt to ping the Linux virtual machines' private ip address through powershell. Requests and replies can be seen. 
</p>
<br />
</p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In order to observe what happens when the inboundings pings are blocked a network security group is enabled to disable inbounding ICMP traffic.  
</p>
</p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Additionally, Secure Shell (SSH) can be simulated here, allowing a user to connect to the Linux virtual machine through the Windows virtual machine. When filtering for SSH traffic in Wireshark, it won’t show any results. However, by executing the command ssh labuser2@10.0.0.5 in PowerShell and using the user's password to log in, you will be able to see the SSH traffic.

  
</p>

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /># azure-network-protocols
