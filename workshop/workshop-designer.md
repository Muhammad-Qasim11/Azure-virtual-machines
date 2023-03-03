


## How to create and deploy Azure virtual machines

## Workshop Source 

We selected to create this workshop based on the following resources from Microsoft Learn Website:

Source 1:https://learn.microsoft.com/en-us/training/modules/create-linux-virtual-machine-in-azure/

Source 2:https://learn.microsoft.com/en-us/training/modules/create-windows-virtual-machine-in-azure/

Source 3:https://learn.microsoft.com/en-us/azure/app-service/quickstart-wordpress

Source 4:https://learn.microsoft.com/en-us/azure/static-web-apps/overview

## Stage 1: Desired Results 

1. Students will be skilled at: How to create and deploy various types of Azure virtual machines like how to create and delpoy Linux VM, Windows VM, Web App and WordPress VM.

2. Students will be able to independently use their learning to: create and deploy fully functional Azure VM and will be able to use them for real world problem solving.

3. Students will be able: to connect Linux and Windows VM with their local machines and will be able to perform tasks on VM's from their local machines.

4. Students will be able: to host WordPress website and can start their blogging journey, either by writing about tech or can publish about their favourite topics.

5. Students will be able: to create their online portfolio by using Azure Web service, which can help them to stand out among other applicants for jobs or internships.

## Stage 2: Evidence

 Students will demonstrate their understanding of the concepts learned by doing the following:
 
1. Short quizes about the concepts learned in each module.

2. Students can use Azure Sandbox or their student Azure subscription for practicing the concepts learned.

## Stage 3: Learning Plan

> Now you are ready to build out your lesson plan. Summarize the key learning events here by creating an outline of the milestones that you can lay out to structure the course.

## Milestone 1: How to create and deploy Linux virtual machine on Azure

## Module Source Link [Licrosft Learn Link](https://learn.microsoft.com/en-us/training/modules/create-linux-virtual-machine-in-azure/2-create-a-linux-virtual-machine)

## Goals

In this workshop, we will discuss *How to Create and deploy Linux Virtual Machine on Azure*.

| **Goal**              | *describe the goal of the workshop*                                    |
| ----------------------------- | --------------------------------------------------------------------- |
| **What will you learn**       | *Creation and deployment of VM*                                        |
| **What you'll need**          | *[Azure Student Account and Mircsoft Learn Account](https://learn.microsoft.com/en-us/training/modules/create-linux-virtual-machine-in-azure/2-create-a-linux-virtual-machine)* |
| **Duration**                  | *2 Hours (Max)*                                                                |
| **Microsoft Cloud Topics taught**                  | *M365, Azure, GitHub, Azure Virtual Machine*                                                                |
| **Just want to try the app or see the solution?** | *an optional link to the completed project sample app or solution folder*                          
 
                         
## Video

Embed your Train the Trainer video here. Instructions on how to create a great video experience is [available on this page](../video-guidance.md).

## Pre-Learning

*[The link to Microsoft Learn for students to pre-learn the topic](https://learn.microsoft.com/en-us/training/modules/create-linux-virtual-machine-in-azure/2-create-a-linux-virtual-machine)*

## Prerequisites

[Read](https://learn.microsoft.com/en-us/training/modules/create-linux-virtual-machine-in-azure/2-create-a-linux-virtual-machine)

## What students will learn

*In this area, describe the scenario and intended solution, paraphrasing what is in the module or creating a brief description here*

Example: We have an existing website running on a local Ubuntu Linux server. Our goal is to create an Azure virtual machine (VM) using the latest Ubuntu image and then migrate the site to the cloud. In this unit, you'll learn about the options you'll need to evaluate when creating a virtual machine in Azure.

*add a screenshot of the completed project*

<img width="707" alt="8" src="https://user-images.githubusercontent.com/76419649/222787799-2f71cd6e-da57-42e6-94fd-ee739aa2b2ae.png">


## Milestone 1 (example)

In this segment, you'll learn to create VM and deploy it on Linux OS.
### 1. Create a new Linux virtual machine
We can create Linux VMs with the Azure portal, the Azure CLI, or Azure PowerShell. The easiest approach when you're starting with Azure is to use the portal, because it walks you through the required information and provides hints and helpful messages during the creation.

->Sign in to the Azure portal using the same account you used to activate the sandbox.
<img width="616" alt="1" src="https://user-images.githubusercontent.com/76419649/222783808-34cab997-2100-4847-9cca-f3b762c006cb.png">

->On the Azure portal menu or from the Home page, under Azure services, select Virtual machines. Alternatively, you can enter Virtual machines in the top search box, and press Enter. The Virtual machines pane appears.

->In the top menu bar, select Create > Azure virtual machine. The Create a virtual machine pane appears.

### 2.Configure the VM settings, add data disks for the VM, and configure the network
![2](https://user-images.githubusercontent.com/76419649/222783597-83c0bc7f-5264-4697-b51a-8a15745c6735.png)

The VM creation experience in the portal is presented in a wizard format to walk you through all the configuration areas for the VM. Selecting Next takes you to the next configurable tab. However, you can move between the tabs at will by selecting them in the sub menu.
After you complete all the required options (identified with red asterisks), you can skip the remainder of the wizard experience, and start creating the VM by selecting Review + create at the bottom of the wizard.

Remember that these instructions use the sandbox. If you're using another Azure portal account, you may need to adapt some details accordingly.

->On the Basics tab, enter the following values for each setting.

->Select Next: Disks to open the Disks tab.

->On the Disks pane, enter the following values for each setting.

->Select Next: Networking to move to the Networking tab.
![4](https://user-images.githubusercontent.com/76419649/222783353-82e90867-3ace-47b1-a947-66ecff7350c6.png)

->On the Networking pane, accept all the default values for each setting.

->Finish configuring the VM and creating the image by selecting Review + create.

->After the system validates your options and gives you details about the VM being created, select Create to create and deploy the VM. The Azure dashboard will show the VM that's being deployed. This may take several minutes.

### You've created a Linux VM in Azure. The next thing you’ll do is configure it for the tasks we want to move to Azure.

Unless you’ve set up a site-to-site VPN to Azure, your Azure VMs won’t be accessible from your local network. If you’re just getting started with Azure, it’s unlikely that you have a working site-to-site VPN. So how can you connect to the virtual machine?

### 3.Get the public IP address of the VM
In the Azure portal from the previous exercise, select Go to resource. The Overview pane for the virtual machine that you just created appears. Alternatively, you can find the VM under All Resources if you need to open it. The overview pane allows you to:

1. See if the VM is running.
2. Stop or restart the VM.
3. Get the public IP address of the VM.
<img width="741" alt="4" src="https://user-images.githubusercontent.com/76419649/222784389-f7444183-4e3f-4d34-b165-f177bb4778c8.png">

4. See the activity of the CPU, disk, and network.
5. Select Connect > SSH at the top of the pane.

Under step 4, copy the command to the clipboard.
<code> ssh azureuser@13.68.150.164 </code>
6. The first time we connect, SSH will ask us about authenticating against an unknown host.
7. <code> The authenticity of host '137.117.101.249 (137.117.101.249)' can't be established.
ECDSA key fingerprint is SHA256:w1h08h4ie1iMq7ibIVSQM/PhcXFV7O7EEhjEqhPYMWY.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '137.117.101.249' (ECDSA) to the list of known hosts. </code>
8. Enter the passphrase you used when you created the SSH key pair.

### 4. Initialize data disks
Any additional drives you create from scratch need to be initialized and formatted. The process for initializing is identical to a physical disk.

-> First, identify the disk that we just created. You could also use dmesg | grep SCSI, which will list all the messages from the kernel for SCSI devices.

-> After you know the drive (sdc) you need to initialize, you can use fdisk to do that. You'll need to run the command with sudo, and supply the disk you want to partition. 
<code>(echo n; echo p; echo 1; echo ; echo ; echo w) | sudo fdisk /dev/sdc </code>

->Next, we need to write a file system to the partition with the mkfs command.
<code>sudo mkfs -t ext4 /dev/sdc1 </code>

### 5.Install software onto the VM
As you can see, SSH allows you to work with the Linux VM just like a local computer. You can administer this VM as you would any other Linux computer: installing software, configuring roles, adjusting features, and other everyday tasks. Let's focus on installing software for a moment.

### 6.Install the Apache web server
Apache is available within Ubuntu's default software repositories, so we'll install it using conventional package management tools:

-> Start by updating the local package index to reflect the latest upstream changes:
<code>sudo apt-get update </code>

-> Next, install Apache
<code> sudo apt-get install apache2 -y</code>

->It should start automatically. We can check the status using systemctl:
<code>sudo systemctl status apache2 --no-pager </code>

->Finally, we can try retrieving the default page through the public IP address. However, even though the web server is running on the VM, you won't get a valid connection or response.

### 7.Update the NSG on the network interface
Port 80 is open on the NSG applied to the subnet. But port 80 is blocked by the NSG applied to the network interface. Let's fix that so we can connect to the website.

->Switch back to the Overview pane for the VM. You can find the VM under All Resources.

->In the left menu pane, under Settings, select Networking.

->You should have the NSG rules for the subnet in the top section, and the NSG rules for the network interface in the bottom section of the same tab. In the bottom section, for the NSG rules for the network interface, select Add inbound port rule.
![3](https://user-images.githubusercontent.com/76419649/222786255-7ecf02fa-065c-462f-900f-2aa1ce44e0d0.png)

-> Fill the details:
![4](https://user-images.githubusercontent.com/76419649/222786563-130b84e8-8666-44d1-9cc9-2d433c876dfa.png)

->Select Add to create the rule. The Networking pane for your VM reappears.

### 8.Open the default webpage
To make an HTTP request, copy and paste the NIC Public IP address of the server into a browser, and press Enter. It should now work.
<img width="707" alt="8" src="https://user-images.githubusercontent.com/76419649/222786759-a0bfbc4a-f71f-40d7-a204-7ffb761fb399.png">


Always make sure to lock down ports used for administrative access. An even better approach is to create a VPN to link the virtual network to your private network, and only allow RDP or SSH requests from that address range. You can also change the port used by SSH to be something other than the default. 


## Milestone 2: How to connect Linux virtual machine with your local machine

## Milestone 3: How to create and deploy Windows virtual machine on Azure

## Milestone 4: How to connect Windows virtual machine with your local machine

## Milestone 5: How to create and deploy WordPress virtual machine on Azure

## Milestone 6: How to create and deploy Web App on Azure
