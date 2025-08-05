<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com/watch?v=9GvWimKQn68)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Network Protocols such as (ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows Azure Edition (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1 - Create a Resource Group and  create a new Virtual Network and Subnet
- Step 2 - Create a Windows 11 Virtual Machine 
- Step 3 - Create a Linux (Ubuntu) VM and select the same Resource Group and Virtual Network—the Virtual Network MUST BE THE SAME.
- Step 4 - Download Wireshark to run Various tests

<h2>Actions and Observations</h2>

<p>
<img src="https://translucentcomputing.github.io/kubert-assistant-lite/assets/images/azure-vm/1_azure-home.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first Step is to log in to Azure using your personal account. Once you're in, you'll create a new Resource Group. Within your resource group, you will create a virtual network and two new virtual machines. One machine using Linux Ubuntu and one using Windows Azure edition.
</p>
<br />

<p>
<img src="https://www.whizlabs.com/blog/wp-content/uploads/2019/08/Creating-a-virtual-machine.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once that has been completed, open Remote Desktop if it's not already installed, and then you will have to install the application to continue. Once you've logged into your VM with your username and password, click on Microsoft Edge and begin downloading Wireshark. Once installed, open Wireshark and start packet capture, then filter for ICMP traffic only.

</p>
<br />

<p>
<img src="https://faq.owens.edu/__attachments/1885306892/Connect%20with%20RDP.PNG?inst-v=5113e176-a620-4885-801c-a2b1f322a2b1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Now we want to retrieve the private IP address of the Ubuntu VM (linux-vm) and attempt to ping it from within the Windows Azure edition VM. Open PowerShell within the Windows VM and type the ping command, then observe the network traffic using Wireshark.
</p>
<br />

<img src="https://pendriveapps.com/wp-content/uploads/Wireshark.webp" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>
  Now we can start getting a little more advanced. We will block ping traffic within Azure. Now, we go to our virtual machine, select Network Settings, and then choose Network Security Groups.
   from here. Now we are going to click inbound security rules. From here, add in the left-hand corner and create a new rule. We want to click on destination port, click destination port ranges, and put an astrict (*) which should stop any pings from coming through. 
</p>

<img src="https://i.sstatic.net/scKiO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Ping is useful in IT because it enables quick testing and verification of network connectivity between devices. Specifically, it:

Checks if a device (like a server or computer) is reachable over the network.

Measures the round-trip time for data packets, showing network latency.

Helps diagnose network issues such as packet loss or unreachable hosts.

Confirms if DNS resolution is working by pinging domain names.

In short, ping is a simple yet essential tool for troubleshooting network issues and ensuring that devices can communicate properly.
