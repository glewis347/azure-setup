<img width="884" alt="Screenshot 2025-01-23 at 7 59 52 PM" src="https://github.com/user-attachments/assets/14983237-8b1a-4703-8a5b-d5f0d3e188f9" />

<h1>Azure Virtual Machine Setup & Configuration</h1>

This project illustrates the creation and configuration of Virtual Machines (VM) in a Virtual Network (Vnet) using the Microsoft Azure platform. It involves creating a Resource Group, a Windows 10 VM, a Linux (Ubuntu) VM, and a Vnet.  This setup facilitates communication between both Azure VMs, and will serve as the base infrastructure for my project on Network Traffic Analysis and Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create a new Resource Group for this project
- Setup and Configure a Windows 10 VM
- Setup and Configure a Linux (Ubuntu) VM  
- Inspect the Vnet/Subnet  
  
<h2>Actions and Observations</h2>
<img width="387" alt="Screenshot 2025-01-23 at 8 10 04 PM" src="https://github.com/user-attachments/assets/886eb6b5-b6c1-4b4b-ae98-8415a69a6a3b" />

---

**1. Access Azure Portal**

Sign in to the [Azure](https://portal.azure.com/) portal and select "Resource groups" on the menu to the left hand side of the homepage.
<img width="726" height="804" alt="1" src="https://github.com/user-attachments/assets/5dd96956-a5e9-456a-b385-d681511fff34" />


**2. Create a Resource Group**


Within the Azure Portal, navigate to Resource Groups creation and select **+ Create**.

<img width="1698" height="804" alt="Screenshot 2026-06-04 at 3 29 25 PM" src="https://github.com/user-attachments/assets/ebf94a89-52e6-49a9-8882-9899bc5e0106" />

Provide a name and region for the Resource Group, then select **Review + Create**.

<img width="989" height="867" alt="Screenshot 2026-06-04 at 3 37 14 PM" src="https://github.com/user-attachments/assets/e71bbeae-5ce3-4dfd-9486-5446b212c99b" />

Select **Create**.

<img width="634" height="865" alt="Screenshot 2026-06-04 at 3 41 02 PM" src="https://github.com/user-attachments/assets/b247850f-c3cf-40bb-bc2d-ee760152d615" />



<br>
<br>

**3. Create a Windows 10 Virtual Machine**

On the Menu to the left of the page, select "Virtual machines"

<img width="695" height="797" alt="image" src="https://github.com/user-attachments/assets/61a74554-baf9-4325-8387-fe0c25639c2e" />

Here, you will see that there are no VMs created (yet). To create the VM, select **+ Create** -> **Virtual machine**

<img width="1644" height="857" alt="image" src="https://github.com/user-attachments/assets/b9a42723-1fa7-431a-815f-b2182b46c0dd" />

To setup and configure the Windows VM, provide the following details:
- **Resource Group**: Select the Resource Group created earlier (RG-Project)
- **Virtual machine name**: Windows-VM (or any name of your choosing)
- **Region**: (US) East US
- **Availability zone**: Zone 3
- **Image**: Windows 10 (22H2)

<img width="1095" height="819" alt="image" src="https://github.com/user-attachments/assets/f732b603-f3ff-4931-8cba-4019a7ef3fab" />

Continuing setup:
- **Size**: Standard_DC2ds_v3 - 2 vcpus, 16 GiB memory
- **Username**: labuser (or any username of your choosing)
- **Password**: choose a secure password
Click the checkbox in the Licensing section, then select **Next:Disks**

<img width="1043" height="877" alt="image" src="https://github.com/user-attachments/assets/e06d0d57-6e68-41a9-b5ab-aa58cd8cafe6" />

Select **Next:Networking**

<img width="1022" height="881" alt="image" src="https://github.com/user-attachments/assets/a921327e-eab0-40ef-b022-39a7456c2b2c" />

In the **Virtual network** field, select **Create new** and provide the following details to create the Vnet:
- **Name**: Lab-Vnet (or any name of your choosing)
Select **OK**
Creating a Virtual Network (VNet) is important because it creates a private and secure network environment for the virtual machines to communicate with each other.

<img width="1917" height="881" alt="image" src="https://github.com/user-attachments/assets/51a05e57-107f-437f-9110-84c850234a90" />

Select **Create**

<img width="994" height="874" alt="image" src="https://github.com/user-attachments/assets/f35e135a-5fdb-4acb-b709-6a5c61fe800a" />

Observe that the VM has been created and placed in our Resource Group:

<img width="1874" height="577" alt="image" src="https://github.com/user-attachments/assets/2ceb163d-9b14-455c-b612-5e85ced36941" />



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
