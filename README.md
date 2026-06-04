<img width="884" alt="Screenshot 2025-01-23 at 7 59 52 PM" src="https://github.com/user-attachments/assets/14983237-8b1a-4703-8a5b-d5f0d3e188f9" />

<h1>Azure Virtual Machine Setup & Configuration</h1>

This project illustrates the creation and configuration of Virtual Machines (VM) in a Virtual Network (Vnet) using the Microsoft Azure platform. It involves creating a Resource Group, a Windows 10 VM, a Linux (Ubuntu) VM, and a Vnet.  This setup facilitates communication between both Azure VMs, and will serve as the base infrastructure for my project on Network Traffic Analysis and Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Resource Group Creation
- Windows 10 VM Deployment
- Linux (Ubuntu) VM Deployment  
- Vnet/Subnet Inspection  
  
<h2>Actions and Observations</h2>
<img width="387" alt="Screenshot 2025-01-23 at 8 10 04 PM" src="https://github.com/user-attachments/assets/886eb6b5-b6c1-4b4b-ae98-8415a69a6a3b" />

---

**1. Access Azure Portal**

Sign in to the [Azure](https://portal.azure.com/) portal to begin provisioning cloud resources.

**2. Create a Resource Group**


Within the Azure Portal, navigate to Resource Groups creation and select **+ Create**. Provide a name and region for the Resource Group, then select **Review + Create**, followed by **Create**.

<img width="1119" height="709" alt="image" src="https://github.com/user-attachments/assets/05caefb6-d866-4866-be2f-aff6908c85da" />

<img width="640" height="447" alt="Screenshot 2026-02-23 213928" src="https://github.com/user-attachments/assets/241b7b32-b05e-41a3-8893-21851b2977fc" />

<br>
<br>

**3. Create a Windows 10 Virtual Machine**

In the Azure Portal, navigate to Virtual Machines creation and select **+ Create**. 
- Provide the following details:
    - **Resource Group**: Select the Resource Group created earlier
    - **VM Name**: Enter a name for your Windows 10 VM
    - **Image**: Choose "Windows 10"
    - **Authentication Type**: Username/Password
- Configure other settings as needed and click **Review + Create**, and then **Create**

<img width="886" height="957" alt="Screenshot 2026-02-23 215051" src="https://github.com/user-attachments/assets/7b59446d-bc9d-49e0-b7f9-4d25fe46ab69" />

<br>
<br>
<br>

In the Networking tab, allow Azure to create a new Virtual Network (VNet) and Subnet, naming the VNet "Lab-Vnet".   
Adding a Virtual Network (VNet) is important because it creates a private and secure network environment for Azure resources like virtual machines to communicate with each other.

<img width="965" height="580" alt="Screenshot 2026-02-23 215423" src="https://github.com/user-attachments/assets/7b525806-aa2e-44a6-acc9-5d17ac869574" />

<br>
<br>

**4. Create a Linux (Ubuntu) Virtual Machine**

In the Azure Portal, navigate to Virtual Machines creation and select **+ Create**.
- Provide the following details:
    - **Resource Group**: Select the same Resource Group used for the Windows 10 VM
    - **VM Name**: Enter a name for your Linux (Ubuntu) VM
    - **Image**: Choose "Ubuntu Server"
    - **Authentication Type**: Username/Password
- Configure other settings as needed and click **Review + Create**, and then **+ Create**

<img width="885" height="1169" alt="Screenshot 2026-02-23 220647" src="https://github.com/user-attachments/assets/6d94436c-cf6b-4e02-a452-7dc8dbce2220" />

<br>
<br>
<br>

In the **Networking** tab, select the previously created Virtual Network and make sure the subnet matches the one used by the Windows 10 VM. 
Using the same Virtual Network (VNet) for both the Windows and Linux virtual machines is important because it allows them to communicate securely over the same private internal network, enabling connectivity testing, shared services, and proper network interaction within the lab environment.

<img width="918" height="850" alt="Screenshot 2026-02-23 220436" src="https://github.com/user-attachments/assets/11a25637-5b95-452b-b3db-649ddff3bddf" />

<br>
<br>

**5. Verify Setup**

- Ensure both Virtual Machines are in the same Virtual Network and Subnet for proper communication. 

After deployment, both virtual machines were successfully created and are running within the same Resource Group and Virtual Network. These components provide the foundational infrastructure for upcoming project tasks.

<img width="910" height="329" alt="Screenshot 2026-02-24 185452" src="https://github.com/user-attachments/assets/c46a5d2a-972f-427b-bd32-f8109ccfdf08" />





<h2>Purpose</h2>

The purpose of this project is to build a foundational Azure cloud environment by deploying and configuring virtual machines within the same Virtual Network and Subnet. This setup enables secure internal communication and serves as a base for future networking, security, and traffic analysis tasks.
