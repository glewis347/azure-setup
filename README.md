<img width="884" alt="Screenshot 2025-01-23 at 7 59 52 PM" src="https://github.com/user-attachments/assets/14983237-8b1a-4703-8a5b-d5f0d3e188f9" />

<h1>Azure Virtual Machine Setup & Configuration</h1>

This project illustrates the creation and configuration of Virtual Machines (VM) in a Virtual Network (Vnet) using the Microsoft Azure platform. It involves creating a Resource Group, a Windows 10 VM, a Linux (Ubuntu) VM, and a Vnet.  This setup facilitates communication between both Azure VMs, and will serve as the base infrastructure for my project on Network Traffic Analysis and Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)
- Ubuntu Server 24.04

<h2>High-Level Steps</h2>

- Create a new Resource Group for this project
- Setup and Configure a Windows 10 VM
- Setup and Configure a Linux (Ubuntu) VM  
- Inspect the Vnet/Subnet  
  
<h2>Actions and Observations</h2>

**1. Access Azure Portal**

Sign in to the [Azure](https://portal.azure.com/) portal and select "Resource groups" on the menu to the left hand side of the homepage.
<img width="726" height="804" alt="1" src="https://github.com/user-attachments/assets/5dd96956-a5e9-456a-b385-d681511fff34" />


**2. Create a Resource Group**


Within the Azure Portal, navigate to Resource Groups creation and select **+ Create**.

<img width="1698" height="804" alt="Screenshot 2026-06-04 at 3 29 25 PM" src="https://github.com/user-attachments/assets/ebf94a89-52e6-49a9-8882-9899bc5e0106" />

Provide a **Resource group name** and **Region** for the Resource Group, then select **Review + Create**.

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

**4. Create a Linux (Ubuntu) Virtual Machine**

In the Virtual Machines section select **+ Create** then **Virtual machine**

<img width="1496" height="657" alt="image" src="https://github.com/user-attachments/assets/55af6ede-db2d-4a08-9481-13c3374342f0" />

- Provide the following details:
    - **Resource Group**: Select the same Resource Group used for the Windows 10 VM
    - **Virtual machine Name**: Enter a name for your Linux (Ubuntu) VM
    - **Region**: (US) East US
    - **Availability zone**: Zone 3 
    - **Image**: Ubuntu Server 24.04

 <img width="1034" height="828" alt="image" src="https://github.com/user-attachments/assets/b40677bf-bb2a-4ded-b658-f843074646ca" />

Select the "Password" radio button for the **Authentication type** and proceed to create a username and password for the Linux VM. Select **Next:Disks**

<img width="1020" height="878" alt="image" src="https://github.com/user-attachments/assets/31088fcc-7237-4d45-9589-4f6784321f9e" />

Select **Next:Networking**

<img width="1019" height="877" alt="image" src="https://github.com/user-attachments/assets/27038d38-f0c6-4aef-81ad-fac93505e17e" />

In the **Networking** Tab, select the previously created **Virtual network** and make sure the **Subnet** matches the one used by the Windows 10 VM. 
Using the same Vnet for both the Windows and Linux VMs is important because it allows both VMs to communicate securely over the same private internal network, and will lay the foundation for our future networking labs.
Select **Review + create**

<img width="1028" height="876" alt="image" src="https://github.com/user-attachments/assets/2f3c13b7-a8fb-47d3-845b-43b02d01b626" />

Select **Create**

<img width="807" height="875" alt="image" src="https://github.com/user-attachments/assets/85dc4b18-62b6-40f4-a94f-fccd0a868023" />

**5. Verify Setup and Configuration**: 

Observe that both VMs are now created and confirm that they belong to the same Resource Group:

<img width="1501" height="417" alt="image" src="https://github.com/user-attachments/assets/50ba06da-73d3-4772-b477-a7b47fb9aa15" />

For both VMs, observe that they are connected to the same Vnet/subnet, and observe their Private IP addresses:

<img width="1050" height="651" alt="image" src="https://github.com/user-attachments/assets/0015a7c6-eebf-4b33-8268-a239710d09ee" />

<img width="1036" height="667" alt="image" src="https://github.com/user-attachments/assets/1b2ec2ed-2a22-4dbf-ab0e-752713ae545c" />

Both VMs are now successfully created and are running within the same Resource Group and Virtual Network.
