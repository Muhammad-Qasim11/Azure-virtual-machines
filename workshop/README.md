# How to create and deploy Azure virtual machines

## Workshop Source 

We created this workshop based on the following sources:

Source 1:https://learn.microsoft.com/en-us/training/modules/create-linux-virtual-machine-in-azure/

Source 2:https://learn.microsoft.com/en-us/training/modules/create-windows-virtual-machine-in-azure/

Source 3:https://learn.microsoft.com/en-us/azure/app-service/quickstart-wordpress

Source 4:https://learn.microsoft.com/en-us/azure/static-web-apps/overview

## Goals

In this workshop, we will discuss how to create and deploy different types of Azure virtual machines. The learners will be able to create Azure virtual machines like Windows VM, Linux VM, WordPress VM and Web app deployment and will learn how to connect different types of VM's with their Local machines.

| **Goal**              | *How to create and deploy Azure virtual machines*                                    |
| ----------------------------- | --------------------------------------------------------------------- |
| **What will you learn**          | *Learn how to deploy various VM's on Azure and how can we use it from our local machine*                                        |
| **What you'll need**             | *Azure subscription,Know how of Azure, Knowledge of various types of Virtual machines* |
| **Duration**                     | *1 to 1.5*                                                                |
| **Microsoft Cloud Topics taught**| *Azure VM's, Azure Web app* |
 
                         
## Video

Embed your Train the Trainer video here. Instructions on how to create a great video experience is [available on this page](../video-guidance.md).

## Pre-Learning

- [Create an Azure account](https://learn.microsoft.com/en-us/training/modules/create-an-azure-account/)

- [Virtual machines in Azure](https://learn.microsoft.com/en-us/azure/virtual-machines/overview)

- [Create a WordPress site](https://learn.microsoft.com/en-us/azure/app-service/quickstart-wordpress)

- [Create a Linux virtual machine in the Azure portal](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-portal?tabs=ubuntu)

- [Create a Windows virtual machine in Azure](https://learn.microsoft.com/en-us/training/modules/create-windows-virtual-machine-in-azure/)

- [What is Azure Static Web Apps?](https://learn.microsoft.com/en-us/azure/static-web-apps/overview)

## Prerequisites

- Azure account
- Azure subscription

## What students will learn

1. Students will be skilled at: How to create and deploy various types of Azure virtual machines like how to create and delpoy Linux VM, Windows VM, Web App and WordPress VM.

2. Students will be able to independently use their learning to: create and deploy fully functional Azure VM and will be able to use them for real world problem solving.

3. Students will be able: to connect Linux and Windows VM with their local machines and will be able to perform tasks on VM's from their local machines.

4. Students will be able: to host WordPress website and can start their blogging journey, either by writing about tech or can publish about their favourite topics.

5. Students will be able: to create their online portfolio by using Azure Web service, which can help them to stand out among other applicants for jobs or internships.



## Milestone 1: How to create and deploy Linux virtual machine on Azure

In this segment, you'll learn to create VM and deploy it on Linux OS.
### 1. Create a new Linux virtual machine
We can create Linux VMs with the Azure portal, the Azure CLI, or Azure PowerShell. The easiest approach when you're starting with Azure is to use the portal, because it walks you through the required information and provides hints and helpful messages during the creation.

->Sign in to the Azure portal using the same account you used to activate the sandbox.
<img width="616" alt="1" src="https://user-images.githubusercontent.com/76419649/222783808-34cab997-2100-4847-9cca-f3b762c006cb.png">

->On the Azure portal menu or from the Home page, under Azure services, select Virtual machines. Alternatively, you can enter Virtual machines in the top search box, and press Enter. The Virtual machines pane appears.

->In the top menu bar, select Create > Azure virtual machine. The Create a virtual machine pane appears.

Example: We have an existing website running on a local Ubuntu Linux server. Our goal is to create an Azure virtual machine (VM) using the latest Ubuntu image and then migrate the site to the cloud. In this unit, you'll learn about the options you'll need to evaluate when creating a virtual machine in Azure.

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

**Step 1: Sign In**

*First go to [azure portal](https://portal.azure.com/) and sign in to the portal.*

**Step 2: Select Virtual Machine**

*Now go to azure services section and select virtual machines.*

![example1](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W1.png)

**Step 3: Create Virtual Machine**

*In the virtual machine section click on create button.*

![example2](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W2.png)

*And then select azure virtual machine.*

![example3](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W3.png)

*After creating the page opens just like the image shown below. If you have any errors opening the page then recheck your previous steps.*

![example4](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W4.png)

**Step 4: Name your Virtual Machine**

*In instances section name your virtual machine and select windows server 2019 in the images tab and leave rest as default.*

![example5](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W5.png)

**Step 5: Set Username and Password**

*Now under administrator account section give username and password.*

![example6](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W6.png)

*Under Inbound port rules, choose Allow selected ports and then select RDP (3389) and HTTP (80) from the drop-down.*

![example7](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W7.png)

**Step 6: Deployment**

*Now select the Review + create button at the bottom of the page.*

![example8](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W8.png)

*Once the validation completed, select the Create button at the bottom of the page.*

![example9](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W9.png)

*Wait until the deployment is in progress.*

![example10](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W10.png)

*Once deployment is completed then go to resources.*

![example11](https://github.com/Bazgha19/Azure-virtual-machines/blob/main/workshop/images/W11.png)

link

## Milestone 4: How to connect Windows virtual machine with your local machine

text

link

## Milestone 5: How to create and deploy WordPress virtual machine on Azure

[Source link](https://learn.microsoft.com/en-us/azure/app-service/quickstart-wordpress)

**Step 1:** First login to your Azure account and you must have a subscription or free credits to create a WordPress website.

**Step 2:** create a separate resource group for your WordPress website in Azure to place all the resources in a single group. From Home tab search Resource groups and click on it.

![1](https://user-images.githubusercontent.com/64436573/229769581-01e552bb-f883-484f-bac3-94b72c1012ea.png)

Then click on “create” to create a new resource group.

![2](https://user-images.githubusercontent.com/64436573/229770583-49d08ec9-d938-413e-903d-32536cc39a3d.png)

Then select the subscription and name your resource group and also select appropriate region for your resource group.

**Step 3:** Go to Home tab and click on “create a resource” to create WordPress VM.

![3](https://user-images.githubusercontent.com/64436573/229770950-0b8dc88f-a613-4504-b3da-bc1fb40bb342.png)


**Step 4:** After clicking on create a resource you will be brought to “Marketplace” tab. Here in the search bar , search for WordPress and click on the very first option.

![Picture4](https://user-images.githubusercontent.com/64436573/229771129-69ae21c7-566c-4d53-b588-1fe3e4a50061.png)


**Step 5:** Then click on create to create a new resource of WordPress.

![Picture5](https://user-images.githubusercontent.com/64436573/229771251-b22b51a3-1e9e-4c98-9a4d-8785b630068f.png)

**Step 6:**  Now select appropriate settings for the resource as shown below

![Picture6](https://user-images.githubusercontent.com/64436573/229771442-80dc2269-cf29-40dd-80d0-71a1fb95943f.png)

![Picture7](https://user-images.githubusercontent.com/64436573/229771514-a664f26b-58d5-43c0-b7b4-1f2c39bfa9b3.png)

Here we will give username and password to connect to our website as administrator.

![Picture8](https://user-images.githubusercontent.com/64436573/229771663-92515720-9c1c-435e-9f59-022fb3d7f950.png)

**Step 7:**  After entering the information we can click on “Review + create” button to create our resource.

![Picture9](https://user-images.githubusercontent.com/64436573/229771760-4752d3e2-cb79-4456-af40-773cc0a05b4d.png)


**Step 8:**  If we want to make further changes to our resource and customize it then we have option for that, by exploring the different tabs available on the “create a virtual machine” page as shown below

![Picture10](https://user-images.githubusercontent.com/64436573/229771977-15318ea2-0e4e-4fed-8715-4be55c36e259.png)


**Step 9:** After clicking on “review + create” button, we can finally create our resource by clicking on the “create” button. 


![Picture11](https://user-images.githubusercontent.com/64436573/229772077-55cb4654-0d91-414d-ac2c-ce7923dd81dd.png)

Here on this page we can review our settings and can see all the information of our resource.


After clicking on create button, deployment of our resource will be stated as shown below


![Picture12](https://user-images.githubusercontent.com/64436573/229772238-ebafa3e2-ad55-4cc6-9301-61ec9ccb41d8.png)


**Step 10:** When the deployment is completed then go to home tab and search for “virtual machine” in the search bar as shown below


![Picture13](https://user-images.githubusercontent.com/64436573/229772327-2281d0bc-e27a-461e-9382-35a8c19cd4bb.png)

When we search for virtual machine then all the virtual machines that we have created will be displayed, then select that virtual machine which we have deployed for WordPress website. Here we have deployed the virtual machine for WordPress website in the name of “wordpress-website”. So, we will select this virtual machine.


**Step 11:**  As we have created “wordpress-website” virtual machine for our WordPress website, so when we click on it then the below screen will be appeared

![Picture14](https://user-images.githubusercontent.com/64436573/229772562-0f5f3d68-c54d-4152-852e-83441e081e9b.png)

Here on this screen we can see that our VM is in running state because the “start” button in the top section of the screen is grayed and the “stop” button is blue, which means that our VM is in running state and we also stop it by clicking on the stop button.


**Step 12:** 

## Milestone 6: How to create and deploy Web App on Azure

## Quiz or Code Challenge

Link to quiz or challenge on Learn

## Next steps

- [Microsoft Certified: Azure Fundamentals](https://learn.microsoft.com/en-us/certifications/azure-fundamentals/)

## Practice

*suggest, or add as an addendum, a way to extend students knowledge of the topic by creating a new app or demo that builds on the original workshop materials.*

## Feedback

Be sure to give [feedback about this workshop](https://forms.office.com/r/MdhJWMZthR)!

[Code of Conduct](../CODE_OF_CONDUCT.md)

