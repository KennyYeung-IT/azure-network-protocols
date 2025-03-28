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

![image](https://github.com/user-attachments/assets/5aa47f0d-8c5c-4193-b39f-809f931f5fd3)
![image](https://github.com/user-attachments/assets/86265616-de8f-47e8-9667-e38ca4da0806)
![image](https://github.com/user-attachments/assets/40f7649d-24c4-4324-a680-d85707576895)

Open the Windows 10 and linux virtual machines via remote desktop connection by gabbing their public ip addresses through the Azure portal, making sure that the virtual machines are on the same virtual network.   
  
</p>
<br />

![image](https://github.com/user-attachments/assets/8668f5a5-9761-4363-806d-71e030fc5df7)

<p>
Install wireshark https://www.wireshark.org/ in the Windows 10 virtual machine.

</p>
<br />

![image](https://github.com/user-attachments/assets/a7ee318b-dfff-4506-bdb1-0ea3c4630e6d)

<p>
Filter traffic by ICMP and attempt to ping the Linux virtual machines' private ip address through powershell. Requests and replies can be seen. 
</p>
<br />

![image](https://github.com/user-attachments/assets/712cbd01-2eee-478b-b0c6-eddaf7abbb0a)

![image](https://github.com/user-attachments/assets/c918803d-17cb-4325-b14b-373d1d90047e)



<p>
In order to observe what happens when the inboundings pings are blocked a network security group is enabled to disable inbounding ICMP traffic.  
</p>


![image](https://github.com/user-attachments/assets/c72dbffb-31dd-421d-bd6c-7d4c74197cad)
![image](https://github.com/user-attachments/assets/a354e74f-98cd-4165-a7ea-2c0b39dc7504)


<p>
Additionally, Secure Shell (SSH) can be simulated here, allowing a user to connect to the Linux virtual machine through the Windows virtual machine. When filtering for SSH traffic in Wireshark, it won’t show any results. However, by executing the command ssh labuser@(private ip address) in PowerShell and using the user's password to log in, you will be able to see the SSH traffic.

  

![image](https://github.com/user-attachments/assets/4d3d5902-4fd6-4f75-bf90-87d1fc12209e)


<p>
Wireshark is also able to filter DNS traffic and we can observe the traffic by putting in the command "nslookup" find the ip address of human domains such as google.com.
</p>

![image](https://github.com/user-attachments/assets/e16d062c-ff45-428e-8c8e-87bcf0d4322b)

<p>
Next, it can filter out DHCP in which we can physically observe the discover, acknowledge, offer, request, and release portion of the traffic. 
</p>


![image](https://github.com/user-attachments/assets/7ad230ac-31d3-4f8e-aa69-5a9519edca8d)


<p>
Finally, filter for RDP traffic in Wireshark, which displays the Remote Desktop Protocol traffic. It shows a constant stream due to ongoing changes in the virtual machine, such as screen updates or user inputs like mouse clicks and keyboard actions.

</p>
<br /># azure-network-protocols
