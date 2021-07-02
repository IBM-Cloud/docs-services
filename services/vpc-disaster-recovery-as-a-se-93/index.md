# About VPC+ DRaaS

### Introduction

[VPC+ DRaaS](https://cloud.ibm.com/catalog/services/vpc-cloud-migration) by Wanclouds provides you with a comprehensive Disaster Recovery as a Service for your IBM Cloud Infrastructure and Resources.

  

Our DRaaS enables IBM Cloud customers to backup their entire [virtual private cloud (VPC)](https://www.ibm.com/cloud/vpc?lnk=STW_US_STESCH_&lnk2=learn_CloudVrtSvrVPC&pexp=DEF&psrc=NONE&mhsrc=ibmsearch_a&mhq=VPC)  resources including network, compute, storage as well as [Kubernetes](https://www.ibm.com/cloud/learn/kubernetes) deployments, and be able to restore it across different regions in the IBM Cloud.

### What Resources can be Backed up and Restored

#### IBM Cloud Virtual Private Cloud

With Wanclouds's [VPC+ DRaaS](https://wanclouds.net/draas) you can backup and restore your entire [IBM Cloud Virtual Private Cloud](https://www.ibm.com/cloud/vpc?lnk=STW_US_STESCH_&lnk2=learn_CloudVrtSvrVPC&pexp=DEF&psrc=NONE&mhsrc=ibmsearch_a&mhq=VPC) construct, configurations and resources such as:

-   VLANs and Subnets
-   Virtual Server Instances (VSIs)
-   Storage Volumes (primary and secondary)
-   Security Groups
-   IBM Cloud Load Balancers
-   Firewall (ACL) Configuration
-   Security Groups
-   VPN Configuration
-   SSH Keys
-   NAT
-   CDN
-   Virtual Machines (VMs)
-   Public Gateway
-   Data Volumes

#### IKS & OpenShift Clusters

With our VPC+ DRaaS you can also backup and restore your entire cluster such as [IBM Cloud Managed Kubernetes clusters (IKS)](https://www.ibm.com/cloud/kubernetes-service) and OpenShift including resources like:

-   Worker nodes    
-   Worker pools    
-   Services    
-   Pods    
-   Namespaces    
-   Secrets    
-   StatefulSets    
-   DaemonSet    
-   Deployments    
-   ConfigMaps    
-   Custom Resource Definitions    
-   Persistent volumes    

And all the other resources and workloads running within Kubernetes.

  

## Prerequisites for VPC+ DRaaS

### IBM Cloud Virtual Private Cloud

Before you begin discovering and backing up your IBM Virtual Private Cloud resources, you must have:

-   Permissions for IBM Cloud classic and VPC.    
-   A [classic infrastructure API key](https://cloud.ibm.com/docs/iam?topic=iam-classic_keys) and an [IBM Cloud API key](https://cloud.ibm.com/docs/iam?topic=iam-userapikey) (VPC API key).  
    Note: Your IBM Cloud API key (VPC API key) must have “Reader, Writer” access. You can verify the level of access in IBM Cloud console by clicking Manage  >  Access (IAM) and selecting Authorizations.
    
-   An IBM Cloud Object Storage (COS) bucket and its Resource Instance ID (service credentials). The COS bucket will be used to store your images and volumes during the migration process and its Resource Instance ID will allow VPC+ DRaaS to access it.
-   Learn how to [set up your IBM Cloud Object Storage here](https://cloud.ibm.com/docs/services/cloud-object-storage?topic=cloud-object-storage-getting-started).
-   Learn how to [grant access](https://cloud.ibm.com/docs/vpc?topic=vpc-migrate-vsi-to-vpc#migrate-prereq-create-service-authorization) between VPC Image Services and COS (only required for primary images and secondary volumes migration).
-   Learn how to create your service credentials and get your Resource Instance ID [here](https://cloud.ibm.com/docs/services/cloud-object-storage/iam?topic=cloud-object-storage-service-credentials).
    

  

### IKS & OpenShift Clusters

Before you begin discovering and backing up your IKS and OpenShift clusters, you must have the following permissions:
-   Ensure that you have the following IBM Cloud IAM access policies.
-   [Administrator platform role for VPC Infrastructure](https://cloud.ibm.com/docs/vpc?topic=vpc-managing-user-permissions-for-vpc-resources). 
-   [Administrator platform role](https://cloud.ibm.com/docs/containers?topic=containers-users#platform) for IBM Cloud Kubernetes Service.
-   [Writer or Manager service role](https://cloud.ibm.com/docs/containers?topic=containers-users#platform) for IBM Cloud Kubernetes Service.
-   [Administrator platform role](https://cloud.ibm.com/docs/containers?topic=containers-users#platform) for Container Registry.
-   [Writer or Manager service role](https://cloud.ibm.com/docs/containers?topic=containers-users#platform) for IBM Cloud Object Storage.   
-   Make sure that the API key for the region and resource group that you plan to create the VPC Gen 2 cluster in is set up with the correct [infrastructure permissions](https://cloud.ibm.com/docs/containers?topic=containers-users#api_key).
    

Next Steps:
Once you have completed all the prerequisites, see Creating your account on VPC+ DraaS.

# How To:

## Creating your account on VPC+ DRaaS

To get started on VPC+ DRaaS, follow these instructions:

1.  Visit [vpc.wanclouds.net](https://vpc.wanclouds.net) and Register an account.

2.  Confirm your email address and login to your newly created account on VPC+ DRaaS. 

3.  Once logged in, you will be redirected to the Summary page where you can add your IBM Cloud account and get started.
    
Next Steps:

Refer to Adding your IBM Cloud Account to VPC+ DRaaS.

## Adding your IBM Cloud Account to VPC+ DRaaS

### IBM Cloud Classic Account:

To add your IBM Cloud Account, navigate to Cloud Accounts from the side menu.

  

![](https://lh4.googleusercontent.com/s1EwASWRYEFATM-Owugu53H7x13yiK31w3XZ_rmztbEFRFBwCmPYH71HVBBvTFR3CliTY-ifRl3wNfbM7iKkd6khR11Wk08Hk4FfIX_Vp_xBHlUDOwAuJvf4CkmGqeoVW7nqeirT)

  

Under the IBM Cloud Classic tab, click on Add Account to add your IBM Cloud account.

  

![](https://lh5.googleusercontent.com/97nYwF6KwPNxPWrnv8GFobjVaG50kPdbCzCNpNLbF1UXn-3AbmeKSFn5guvNVPCK6SGY7tpvQfbAK6IYxC8ESzsz4TdlnaVSx0KKvQTA1bsWno1iNmH2myHYe3jFyK6hKjJXCKRS)

  

Give this account a Name and enter the Username and API Key of your IBM Cloud classic infrastructure. This will be used to discover the resources of your current IBM Cloud classic environment.

### IBM Cloud VPC Account:

Under the IBM Cloud VPC tab, click on Add Account to add your IBM Cloud VPC account.

![](https://lh3.googleusercontent.com/Fcx7HXXXTqQ_zdQFpkfOXVjig5IPpEipm9tGsfnNqEaeZL1evh0sFWSu7z8PLN3t__yyNQ0027t8b-c7Cl3Ym6fog36HWXPwnSA9wBf0bEAObdqtc_wuLjvWD1NkMaw0PSYBmm4L)

Give this account a Name and enter the IBM Cloud API Key and your IBM Cloud Object Storage (COS) Resource Instance ID.

  

In order to discover your existing IKS clusters from your IBM Cloud environment, you will also need to add the Access Key ID and Secret Access Key of your IBM Cloud VPC Account.

  

### Next Steps:

Once you have added your IBM Cloud account, you are all set to use the Disaster Recovery as a Service for your IBM Cloud Infrastructure and Resources.

  
  

## Taking a backup of your IKS Clusters

To Discover & Backup your IKS Clusters, navigate to Disaster Recovery from the side menu  and select Discover IKS Clusters tab.

  

![](https://lh4.googleusercontent.com/W_0R87Z5maf7PYKID8MZu5kKO4F_u1xKmk_9eoWbx4nDeoK0KRCUuE8CmkYGN68SG-lSlYnyfolht_xWnzqIPthbWfu_7uzpmYzzhWnTTyUnB6hoJgvheAkBVKledGIjI-dfueHm)

  

Start the discovery process of your existing IKS Clusters by selecting your desired Cloud Account and Region and click on Discover.

![](https://lh4.googleusercontent.com/n65jZ3yglaJqrMBSF87tbViVVdWiW6v2VLaY4SJLkVdo2QHN_g5dF6Q0TcVBBWm7EXe8-glwV6CnPXaetSo4Uj3pXbHA64LurVFE8BI5CZJdo4iKVyroGB76cCvuHh52fZSHKsoL)

  

Once the discovery is complete, select a VPC from the list to view all of its discovered IKS Clusters. Next, click on your desired IKS Cluster to view the detailed information of the Workloads present in the cluster and their respective Namespace, Pod, SVC and PVC.

  

![](https://lh3.googleusercontent.com/DN_ZHYzoAPTev5mlyt0G6SmeiGZV6MBnJAJPwpSeJODnHtTSQrJdL-HdNr2wxduvFYWdnHTGMnRz1nqGycKeSN-adT2KoTOkz_PTyQ1ZAzKeDzpU5BB4fiAXYWSPNlA4GDRi7dOZ)

  

Next, select the Workloads you want to backup and click on Create Backup. Give your backup a Name and click Confirm and Backup.

  

![](https://lh5.googleusercontent.com/oIR2g2R44ujeRW8382i61pOQAMXCbI9nrRSZui2PkaueX4v3SVyjCLtdHFknizjhX6Jc-2SSKzHhySSTr8ElQVvzW3xoHHp0FBnKFVdBtt5OuxQwQ_6ZM5MENLl2Vhmq4yNkijJ4)

  

Once the backup of your workloads is created, it will be displayed under the IKS Cluster Backups tab in the respective Cloud Account.

Next Steps:

In order to Restore your Backed up clusters, see Restoring your IKS Clusters.

## Restoring your IKS Clusters

In order to restore workloads from your IKS Cluster backup, navigate to IKS Cluster Backups tab and select your desired Cloud Account to view all the created backups of the clusters in that specific environment.

  

![](https://lh4.googleusercontent.com/yNFswl_Yg4APi12YtiS_tl9cX9mayMzhwG1js2A-xlg7c8ZPFEEjrsHusf1RT8WENOVF5I6Y6U8QYwt1-kgCrnJeR1G4DcRukB0COaJZqu4pq6XAev9W8YEc2XT2IQvpA23YkpAd)

  

Click Backups to view the list of all the created backups. Next, select your desired cluster backup and click Restore.

  

Note: You can also create a new backup of the workloads from this screen by clicking on Namespaces.

![](https://lh5.googleusercontent.com/hVz4vackPaz3D-PWDqu1ewi6dublabv1imfIjxyfFufvrAvX6LFi6YxBwFO52OJJAdtGmZ0nUX8W3SyR8D8tI1WXrEsvsjzF82hEsd8oiQVlKtAy58wiTND1ZkJebtON8Bk4nocn)

  

Complete the restoring process by following these steps:

  

1)  Give your VPC a Name.

2)  Select the target Region and Zone where you want to restore the workload

3)  Select a Resource Group and click Restore

  

![](https://lh4.googleusercontent.com/pNJTDq0v7z07ID230HaAqfp_i8EB9Gf8IsdxnGwQqMiwXKvdC_9Lt7qS3Nq9wuaRwjkz5vCX5gMqluyNq9fUDxlSEXI1mteWfdH7sdSlEUB2S8dbaBX9AGKVymUOJ_S3B1yB02m9)

  
As the backup restore process starts, you will be shown all of the validated and provisioned resources and errors, if any, in the Report section on the right.

---

copyright: 2021 All Rights Reserved

years:  2021

lastupdated: "07/02/2021"

---





