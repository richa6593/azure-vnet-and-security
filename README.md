Azure Networking Project: VNet, Firewall, VM with Nginx & Bastion Server


Overview


This project demonstrates how to set up a secure network architecture in Azure by creating a Virtual Network (VNet) with a Firewall, a Web Subnet, and a VM behind the firewall. The VM is configured with Nginx to host a static HTML page. Access to the VM is restricted via private IP, and only authenticated end users can bypass the firewall and access the VM using Azure Bastion.

Key Components
VNet (Virtual Network): A secure network environment within Azure.
Azure Firewall: A stateful, cloud-native firewall used to protect resources by filtering network traffic.
Web Subnet: A subnet where the web server (VM) is placed, behind the firewall.
VM (Virtual Machine): A Linux VM with Nginx installed to serve a static HTML page.
Azure Bastion: A fully managed RDP/SSH service that provides secure access to the VM over SSH without the need for public IP addresses.
Nginx: A web server installed on the VM to serve the static page.

Project Steps:

1. Create a Virtual Network (VNet)
Set up an Azure VNet to host your resources. Define the necessary subnets:

Web Subnet: This subnet will contain the VM running the web server.
Firewall Subnet: This subnet is for Azure Firewall.

2. Deploy Azure Firewall
Configure Azure Firewall to protect the network by filtering inbound and outbound traffic. The firewall will block direct access to the web subnet.

3. Create a Web Subnet
Add a Web Subnet within the VNet where the VM will reside. This subnet is isolated by the Azure Firewall.

4. Create and Configure VM (with Nginx)
Create a Linux-based VM within the Web Subnet:

Install Nginx on the VM.
Host a static HTML page on Nginx, which will be accessible to users after connecting via Bastion.

5. Setup Azure Bastion for Secure SSH Access
Since the VM only has a private IP, it cannot be directly accessed over SSH. Azure Bastion provides secure and seamless SSH connectivity to the VM:

Configure Azure Bastion in the same VNet.
Allow authenticated users to access the VM securely via Bastion without needing public IPs.

6. Test the Setup
Verify that the firewall blocks direct access to the VM.
Connect to the VM using Azure Bastion and SSH into the VM.
Ensure that the Nginx web server is serving the static HTML page successfully.


Prerequisites
Before starting the setup, ensure you have:

An Azure account.
Proper Azure permissions to create resources like VNets, Firewalls, VMs, and Bastion.
