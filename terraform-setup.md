# Terraform on Azure

### Document Information

- Created by: Am Aqno
- Reviewed by: 
- Capability: Terraform
- Tools: Linux, Terraform, VSCode

### Version History

| Version | Updated by | Date | Modifications |
|-------|:-------------|:-----|:-----|
| 1.0 - Draft | am aqno | 10/06/2020 | |

## Overview

Contains how to set-up Terraform

### General Information


### Setup pre-requisites 

Reference URLS:
https://docs.microsoft.com/en-us/windows/wsl/install-win10
terraform.io


1. Enable the Windows Subsystem for Linux
   Powershell Admin run 
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
   restart 
   
   *Update to WSL 2 - make sure you are using Windows 10
   Enable Virtual Machine feature run
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   
   Download Linux kernel package
   https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
   Run as Administrator
   
   Set WSL 2 as your default version
   Powershell Admin run
   wsl --set-default-version 2
   

2. Install OS - Ubuntu 20.04 LTS   https://www.microsoft.com/store/apps/9n6svws3rx71
   Setup new user and password.
   user: vm-admin
   
3. Install Windows Terminal. Launch. Dropdown choose Ubuntu. (optional)
4. Enable Remote- WSL on Visual Studio Code.
   Remote-WSL: New Window
   
Install Terraform
1. Download
   wget https://releases.hashicorp.com/terraform/0.13.4/terraform_0.13.4_linux_amd64.zip
   
2. Unzip. If unzip is not available install by running "sudo apt install unzip"
   sudo unzip terraform_0.13.4_linux_amd64.zip

3. Change permission
   sudo chmod +x terraform
 
4. Move terraform to /usr/local/bin
   sudo mv terraform /usr/local/bin
   
5. Run "terraform" to verify terraform is available


Install Azure CLI
Ubuntu:  curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash

Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'; rm .\AzureCLI.msi


Install VSCode extensions
- Remote-WSL
- HashiCorp Terraform hashicorp.terraform

Course Files
https://github.com/in4it/terraform-azure-course

Azure provider
https://www.terraform.io/docs/providers/azurerm/index.html



Azure 
Network - first resource , Azure reserves following addresses
1. x.x.x.0 Network addresses
2. x.x.x.1 Azure default gateway
3. x.x.x.2 and x.x.x.3 azure to map the azure dns ips to the Vnet space
4. x.x.x.255 broadcast addresses








