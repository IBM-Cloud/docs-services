---

copyright:

  years:  2018

lastupdated: "2018-09-06"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About Leanides
{: #gettingstarted}



![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/Leanides-Logo_a5db2a3d-8d2e-4a46-a0d2-78d772b5d7f6.jpg)

Leanides provides a turn key Network Automation solution with utilities that
 give Network, Helpdesk and Desktop Support staff the autonomy to perform
 rapid network device operations and data retrieval for network maintenance
 and troubleshooting with a high level of proficiency and accuracy.

Leanides software is designed to empower the user with increased functionality through its powerful automation engine. The result is faster resolution of network issues and increased uptime of end users.

This delivers savings to your organization that give you
 the competitive edge in business and the increased uptime of users
 means higher productivity and increased user satisfaction.

Leanides is now available as a Private Cloud or bare metal server installation from a downloadable ISO image.

{:shortdesc}

## Getting started

1 Minimum Recommended Resource Requirements


1.1 Client PC Operating System
The Leanides Client software application is compatible with Windows 7, 8 and 10.

1.2 Network Access Switches
The Leanides network management system is compatible with a wide range of Cisco access switches including these models (Cisco 2960G, 2960S. 2960X, 2950).
(NB. Leanides functions can only be performed on Cisco switches.)

1.3 Server Requirements

Medium Size Network (30 Cisco Switches) – 3 Sites
• Physical Hardware or Virtual Machine
• 2 dedicated CPU cores
• 4 GB memory
• 32 GB disk (fixed size)

Large Size Network (60 Cisco Switches) – 6 Sites
• Physical Hardware or Virtual Machine
• 4 dedicated CPU cores
• 8 GB memory
• 32 GB disk (fixed size)

1.4 Virtual Machine Installation Option - Requirements

Leanides has been designed to operate within a Private Cloud virtual machine environment. The Leanides Network Management System uses a Client-Server architecture model to deliver the service. The Leanides client software application is installed on a local Windows PC for each user of the Leanides software subscription. 

Leanides recommends the following settings for a Private Cloud virtual environment:

Host PC/Server BIOS must be configured to allow Virtual Networking

VM Setup configurations on Private Cloud:

·	CPU: 2 CPU core (64bit, dedicated CPU to the VM)
·	Number of cores per processor 1
·	Memory: 4 GB
·	Disk: 32 GB (fixed size only, not dynamically resized)
·	Guest Operating System - Linux
·	OS Version: Other Linux 2.6 x Kernel 64-bit
·	Hard Disk: SCSI 
·	IO Controller Type: LSI Logic
·	Network Type: Bridged Networking


 Recommended VM environments for Private Cloud setup:

·	VMware (Workstation Pro or Server)
A free evaluation version of VMware Workstation Pro can be downloaded from the website at vmware.com

The options for the Leanides Server installation as a Private Cloud VM are:

For a Single User License subscription

Install Leanides Server as a VM on VMware Workstation Pro: Install the Leanides Server as a VM guest system within VMware Workstation Pro on a local PC. This can be installed on the same PC that the Client application is installed on or on a dedicated PC within the office. For single user license subscriptions, setting up both Client and Server applications on the same PC is the best choice. The method for setup of Leanides Client software is described in Section 2 of this guide.

The method of installation of Leanides Server on VMware Workstation Pro will be described in detail in Section 3 of this guide, as it is a readily available and cost effective method of deployment.

For a Multi-User Team License subscription

Install Leanides Server on a dedicated Virtual server within your LAN. For simplicity of setup and operation, it is recommended to install the Leanides Server within your firewall perimeter on a private cloud. This method is most suitable when a team license is used, as the architecture is more scalable to deliver the service from a central location with close proximity to the core switch infrastructure.

The Leanides Server ovf and iso image files are contained in [Leanides-Cloud-Server.zip]  and it must be downloaded from the website at leanides.com to be used as a repository iso image file in the VM setup.

Software Installation Guide

2 Leanides Server Software Installation

2.1 Private Cloud Environment

Setup Guide for VM - How to Install and Configure Leanides Server in a Virtual Environment

Visit vmware.com to download a free evaluation version of VMware Workstation Pro.

Install VMware Workstation Pro on your local Windows PC or on a dedicated Windows PC on your LAN. The PC that you choose for the installation must have network connectivity to the LAN switches that you wish to manage.

The server image file [Leanides-Cloud-Server.zip] must be downloaded from the website at leanides.com in order to be used as an ovf format repository image file for the VM setup.

Extract the downloaded Leanides-Cloud-Server.zip file to a local directory.

1.	In Workstation Pro, select File > Open. 
2.	Browse to the Leanides.ovf file and click Open. 
3.	Type a name for the virtual machine, type or browse to the directory for the virtual machine files, and click Import. 

Workstation Pro performs ovf specification conformance and virtual hardware compliance checks. A status bar indicates the progress of the import process.  
After Workstation Pro successfully imports the ovf virtual machine, the virtual machine appears in the virtual machine library.The iso image from Leanides-Cloud-Server.zip should be used as the repository for the VM.

Start the VM and wait for it to load.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/1_4af1dbed-6b08-48a5-b78b-02e7cb138d05.png)



At the login prompt type user and press [Enter]

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/2_3145ec2b-c4d2-4925-aede-731ec71a587c.png)



At the password prompt type password and press [Enter]. (The default password is password)

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/3_8d1f2852-5bbc-4840-8c92-20c421b26aa2.png)



Type S and press [Enter] as prompted to configure Static IP settings.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/4_ca9eccc3-60b7-4617-b9f8-faddfc66f20a.png)



Enter the IP address for the VM. (This IP address should be on the same subnet as the external network that it is bridged to for it to communicate with devices on the external LAN.)

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/5_0a60dcab-3577-4320-998b-74c9b39a4709.png)



Enter the Gateway IP Address. (For the VM, this would be either the switch's IP address or the interface IP address of the Vlan on the switch, which should be on the same subnet and Vlan as the VM IP address.)

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/6_1e1b63d6-d7b3-450c-a2bc-dfc6fc920454.png)



Enter the subnet mask for the VM IP address.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/7_233f7e01-7dd7-4900-8a8d-dc2641e7bdc5.png)



Enter the network that the VM IP address is on. (This must be consistent with the gateway IP address, as they need to be on the same subnet.)

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/8_2ff1c6b1-e9e3-417c-a9b9-b9b1ebc6d6cb.png)



Enter the broadcast address for the VM.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/9_40f99f0e-4616-4bea-94f1-fa11ae48dc6d.png)



The VM IP address configuration is now complete. The VM must now be rebooted to apply the settings. Choose restart guest from the top menu to reboot.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/10_cc247063-bf7c-416d-ba23-5078b9ab9b39.png)



![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/11_b6018f7a-77f8-4628-a7cf-a305af36e5c3.png)



After the VM has rebooted, login again as user with password (password)

Press [Enter] twice to get to command prompt.

Type ifconfig and press [Enter]

The output will show the IP address settings that you made. If they are incorrect, they can be changed by rebooting the VM and going through the configuration sequence again as outlined above.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/12_0615053d-f87f-4d91-a154-ec33d4722197.png)



Change password. You can now change the password from its default by typing passwd then press [Enter] and follow the prompts.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/13_afd7bbed-9a6c-421d-bff6-02ce84642352.png)

Follow the prompts and enter the old (current password): password
Then type in the new password when prompted. (Please remember the new password as the VM would need to be reinstalled to if it's forgotten.)

This completes the VM Server setup and you are now ready to login to the Client application as detailed on Section 3. The following section on network connectivity will assist with connecting the Leanides Server with the LAN switch.

This Leanides network management system is designed to enhance the user's ability to manage an enterprise network that uses Cisco switches on the LAN. Network connectivity from the Leanides Server VM to the switches and to the local PC over Ethernet are necessary to utilize the functions of the Leanides Client application. This guide describes the settings required to co-ordinate this 3 way connectivity over Ethernet.                                                                                                                                                  
                                                                                                                                                                                                                                                                                                                                      Step 1. Click on the VM in the left Console panel to show the configuration settings for the VM.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/14_5cba87e7-c56d-4fe3-b3df-5b57d38cb400.png)

Step 2. Double click on Network Adapter to show the settings for the VM network interface.



Step 3. The network setting should be for Bridged network. Note the VM network interface that is being used (VMnet0) as shown in the diagram below.

 Check the box for Replicate physical network connection state and press [Ok] at the bottom of the panel.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/15_943b0565-71a3-4099-893e-3070cfa76e36.png)

Step 4. From the top toolbar select Edit - Virtual Network Editor

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/16_3eb0ec1a-c760-442f-a841-d1ca5e2be3aa.png)

Step 5. Left click to highlight the VMnet interface that is being used as was noted in Step 3, this was VMnet0. Then click on Change Settings from the tab at the bottom of the panel.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/17_3f64e1a4-730f-4d31-b426-5e8780789e36.png)

Step 6. Select Bridged and Automatic and press Ok. The Automatic Settings tab can be clicked to define the network connection type to use.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/18_3c1386a7-3bbb-45ca-b3b0-597728239cf2.png)

Step 7. Power on the VM by clicking the tab on the right panel of the VM console.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/19_a9497f22-aea3-4a10-acca-fb6526ed4bfd.png)

Step 8. After the VM has started up, login to the console as user and enter the password.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/20_8d2d6023-7fc1-4b39-9571-82a0567700bb.png)

Step 9. Press [Enter] twice to go to command line.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/21_d7ecddf0-f245-49fa-952d-d569bbae3c65.png)

Step 10. On the command line type route -n and press [Enter]

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/22_9bed6e0c-5933-4f59-a689-587f3ee21cfa.png)

Step 11. The top line shows the default gateway that was entered during the configuration settings stage.
To test the VM server's network connectivity to the gateway, type ping [Gateway IP Address] as shown.
Press [Ctrl] + [C] to stop the ping.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/23_b0ff39ac-21a1-4db1-ab96-b726e45aebec.png)

As shown, the ping to 10.42.0.5 was successful in going from the VM server to the IP address of the physical network switch.


This completes the Network Connectivity Guide for establishing network connectivity between the VM Server, local PC and the network switch that comprises the gateway IP address setting on the VM Server.


How to install Leanides Client on Windows PC

To access the functions on the Leanides Server, the Client application must be installed on a Windows
PC. The Leanides Client software application is compatible with Windows 7, 8 and 10.

Step 1. Download the Leanides Client Software Application from the Leanides website's download page.

Step 2. Unzip the Leanides Client zip file and extract the contents to a local directory.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/24_96e75ced-cbc7-48ee-b132-6b8e33b71648.png)

Step 3. Double click on the setup.exe file to install the Leanides Client Software.

Step 4. Complete the installation sequence as prompted.

Step 5. Double click on the launch icon that has been installed on the desktop to launch the Leanides Client Application.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/25_598c3c22-1c50-42b9-96f5-875878aa9de5.png)

Step 6. The Leanides Client Software application will start and you will be prompted to enter a License Key.

Step 7. Enter the License Key to complete the installation. You must be connected to the internet for the License key to be validated online.

Step 8. After the License key has been validated, the Client Software Application will open and you will see the Leanides splash screen as it loads.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/26_8744120b-fe1c-4ab1-acd5-e777b59211ed.png)

Step 9. After the Leanides Client software application has loaded you will see the Toolbar and display window.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/27_9738dbb2-fb09-4bca-b6c3-4586d34a2f4f.png)

Step 10. Select Menu on the top toolbar and click Configure.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/28_6ee8e4af-6824-40ba-9f2a-2dee32f6d175.png)

Step 11. The configuration page will open and you may enter the static IP address of the Leanides Server that you will communicate with on the network.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/29_617841f9-e7df-46bd-8be6-c5c47d6e0588.png)

Step 12. When the server has been installed and configured you can test the network connectivity to the server by clicking Test on the top toolbar and selecting View Test Page.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/30_bbf220ca-cd6c-4190-8fa2-256c3433e444.png)

When the Leanides Server VM can connect to your local PC over the Ethernet network, you will see the message below.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/31_07b3b269-524a-46ac-9798-0abc899717be.png)

Step 13. From the left corner of the top toolbar select Main Console.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/32_d699ea86-426e-49f7-9c49-5e348083a668.png)

Step 14. From the top toolbar click on Connect. You should now see the Welcome message of the Leanides Server.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/33_9e2e5527-9b24-4342-8b55-561df473d5d4.png)

Step 15. After reading the Terms and Condition check the Accept checkbox and press [enter]

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/34_c579918f-f3cb-4e70-82bb-d4ddfa6e0919.png)

Step 16. Select the number of sites to manage and press [enter]

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/35_576b9a01-6b44-4ba8-b5d3-eb16c2267d18.png)

Step 17. The site capacity has been prepared and you are ready to login to the Leanides Server.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/36_889cfb2f-6b23-4e16-9920-c0632827d3b6.png)

Step 18. Press Connect on the top toolbar.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/37_6e64704f-81da-4d1b-b8b0-29546dbb9df1.png)

Step 19. Type admin for both username and password and press [Enter]

Step 20. You are now successfully logged into the Leanides Client Application console.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/38_7aa5d8e2-b12d-4d6d-a57c-bc8c8e423a51.png)



How to upgrade Leanides Server software from Trial to Full Version

Please note that updates and upgrades are both done using the following method and so the term may be used interchangeably in the following guide..

Step 1. Login to the Leanides Client application

Step 2. From the top right corner icon select Updates

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/39_52f1596f-b1af-4a00-b1c2-702dfed476e9.png)

Step 3. As described by the message select Menu from the top toolbar. Then Select Configure and 
click on the Menu again and select Activate Server Updates.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/40_90a3aff0-4fea-46ad-bf5e-e6ddb2eb847c.png)

Step 4. You should then see the message that tells that updates have been enabled.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/41_3bf87cd6-df3a-404c-9440-2bf2f9ce5bb8.png)

Step 5. Click on the back arrow at the top left of the panel and press Connect to login again.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/42_ef8a891c-3d77-41ba-a5ac-c403b8c30bdb.png)

Step 6. Click top right corner icon again and select Updates

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/43_b0ad73cf-9ff9-473b-9580-3e28511c235c.png)

Step 7. You should now see the updates page of the Leanides Client Application. Press Enter to commence Step 1. Upload Updates

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/44_61ec6df3-e588-46ae-a791-58eb8d838df1.png)

Step 8. When you have the upgrade .tar file ready on your local PC, press browse to load the file.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/45_dc343d52-f555-44fd-ab05-98f1fb2ff8a4.png)

Step 9. Double click on the upgrade file and press open.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/46_ddda8f4e-7919-47ab-9f8d-84a010734b02.png)

Step 10. Click once on Upload file to upload to Leanides Server.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/47_7ea15456-f3e6-4126-8e37-b5926f85dd17.png)

Step 11. You should then see the validation message.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/48_1060afcf-75b3-4cc1-bd66-5d712e0446cf.png)

Step 12. Once again click on the top right corner icon and select Updates to return to the updates page.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/49_176affc6-ca6a-4666-90dd-b594c0ec3447.png)

Step 13. Click on the View File tab in Step 2. Install Updates and select the update file.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/50_8a6c761c-3be1-4e40-ac51-07e1f6f629a0.png)



![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/51_1e4b9de2-c861-4966-8d06-38cb4a86710a.png)

Step 14. Press Reboot to install the upgrade file. Then close the Leanides Client application.


Step 15. Allow 3 minutes for the reboot and upgrade sequence to complete and then restart the   Leanides Client application, press Connect and login again.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/52_7fa89191-cb20-4b68-950f-ee5fa0775a2c.png)

Step 16. You should now see the Full Version features of the Leanides Server.
To verify, click on Device Login Settings on the main panel and the connection type options should now be Telnet and SSH. This shows that the Full Version features are now activated and ready to use.

![Documentation image](https://mp.s81c.com/8034F2C/dal05/v1/AUTH_db1cfc7b-a055-460b-9274-1fd3f11fe689/markdownBuilder_image_/53_444408da-8051-4311-93ce-320d66b8e8f3.png)

That concludes this guide on how to install Full Version upgrades on the Leanides Server.