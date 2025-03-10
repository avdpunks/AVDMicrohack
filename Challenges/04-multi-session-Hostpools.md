# Exercise 4: Create a host pool for multi-session
[Previous Challenge](./03-start-VM-on-connect.md) - **[Home](../Readme.md)** - [Next Challenge](./05-Implement-FSLogix-Profile-Solution.md)

## Introduction
In this challenge you will create Microsoft Entra ID joined pooled desktops from a custom golden image created in [Challenge 2](./02-Create-a-custom-golden-image.md). For higher sophistication we use the Azure Compute Gallery to provide the golden image and after deployment you will connect to the session host with multiple user and verify if the changes you included in the golden image are in place. Then you will also provide remote apps to your users.

## Challenge
Create multi-session Hostpool joined in Microsoft Entra ID
- Region: Sweden Central  
- Metadata located in West Europe  
- Host Pool type: Pooled
- Choose your Azure Compute Gallery image from the previous challenge
- Domain to join: Microsoft Entra ID (Enroll with Intune “No”)
- Register desktop app group to new workspace
- Assign users

Login to the session host
- Login as a user (Assign user access to Host Pools)
- Verify if VScode and Notepad++ is installed

Deploy Notepad++ and VSCode as Remote App

## Success Criteria
1.	Host Pools are created and Session Hosts are showing available
2.	Users are assigned to the appropriate application group of the host pool
3.	Able to show the Host Pool settings configured
4.	VMs are joined to Microsoft Entra ID
5.	Users can sign in to the VM
6.	Notepad++ & Visual Studio Code are installed on all VMs within the pooled Hostpool and can be accessed via RemoteApp
   
## 💡 Pro Tipps 💡
> **1.** We are deploying an EntraID only host pool. In this case you have to set IAM (RBAC) rights on the resource group level. [More information here](https://learn.microsoft.com/en-us/azure/virtual-desktop/azure-ad-joined-session-hosts#assign-user-access-to-host-pools)

> **2.** If you are trying to access your virtual desktop from **Windows devices or other devices that are not connected to the same Entra ID tenant**, add **targetisaadjoined:i:1** as a custom RDP property to the host pool. [More information here](https://learn.microsoft.com/en-us/azure/virtual-desktop/deploy-azure-ad-joined-vm#access-azure-ad-joined-vms)

## Learning Resources
- [Create Azure Virtual Desktop Hostpool](https://learn.microsoft.com/en-us/azure/virtual-desktop/create-host-pools-azure-marketplace)
- [Capture an image of a VM using the portal](https://learn.microsoft.com/en-us/azure/virtual-machines/capture-image-portal)
- [Manage app groups for Azure Virtual Desktop portal](https://learn.microsoft.com/en-us/azure/virtual-desktop/manage-app-groups)
- [Deploy Microsoft Entra joined VMs](https://learn.microsoft.com/en-us/azure/virtual-desktop/azure-ad-joined-session-hosts#deploy-microsoft-entra-joined-vms)
- [Connect to Azure Virtual Desktop with the Remote Desktop client for Windows](https://learn.microsoft.com/en-us/azure/virtual-desktop/users/connect-windows?tabs=subscribe#install-the-windows-desktop-client)
