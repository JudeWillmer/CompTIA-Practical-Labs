# Introduction to Virtualization and Cloud Technologies

## Overview

This lab covers the practical tasks I completed to explore **virtualization and cloud technologies** using **Amazon Web Services (AWS)** and **Microsoft Azure**. I used the **AWS Management Console** to create Virtual Private Clouds (VPCs), configure subnets and networking components, deploy a **Windows Server EC2 instance**, and remotely access the virtual machine. I also explored the **Microsoft Azure portal**, deployed and connected to a **Windows Server virtual machine**, and reviewed additional configuration options including storage, compute sizing, and backup. These tasks gave me practical experience with **Infrastructure as a Service (IaaS)**, cloud infrastructure provisioning, virtual networking, virtual machine deployment, and remote administration.

---

# Exercise 1 - Configure an AWS Virtual Private Cloud and EC2 Instance

## Objective

Create and configure an **Amazon Virtual Private Cloud (VPC)** with public and private subnets across multiple Availability Zones, deploy a **Windows Server 2022 Amazon EC2 instance** within the VPC, configure the required network and security settings, and establish remote access to the cloud-hosted server using **Remote Desktop Protocol (RDP)**.

---

## Implementation

I used the **Amazon VPC** console to create a new virtual network named **ACIVMLG-vpc** with the IPv4 CIDR block `172.16.0.0/16`. I configured the VPC across two **Availability Zones** with two public and two private subnets, providing separate network segments for resources requiring public or private connectivity. The configuration also included route tables, an internet gateway, and a NAT gateway to support routing and external connectivity within the cloud environment.

After defining the network architecture, I created the VPC resources and verified that AWS successfully provisioned the required networking components. This included the VPC, subnets, route tables, internet gateway, NAT gateway, Elastic IP allocation, and associated routes.

I then used **Amazon EC2** to deploy a **Windows Server 2022** instance into one of the VPC's public subnets. I configured the instance with a key pair, enabled automatic public IP assignment, and created a security group to control network traffic to the instance.

Once the EC2 instance was running and had passed its AWS status checks, I used the instance's public DNS information and **Remote Desktop Protocol (RDP)** connection options to establish a remote session. I successfully accessed the Windows desktop of the cloud-hosted server, confirming that the instance and its supporting network configuration were operational.

---

## Navigation

```text
AWS Management Console
  ↳ VPC
    ↳ Create VPC
      ↳ VPC and More
        ↳ Configure IPv4 CIDR
        ↳ Select Availability Zones
        ↳ Configure Public and Private Subnets
        ↳ Configure NAT Gateway
          ↳ Create VPC

AWS Management Console
  ↳ EC2
    ↳ Instances
      ↳ Launch Instance
        ↳ Windows Server 2022
          ↳ Select Key Pair
          ↳ Select ACIVMLG VPC
          ↳ Select Public Subnet
          ↳ Enable Public IP
          ↳ Configure Security Group
            ↳ Launch Instance

EC2
  ↳ Instances
    ↳ ACIVMLG
      ↳ Connect
        ↳ RDP
          ↳ Connect to Windows Server
```

---

## Outcome

I successfully created a multi-subnet **AWS VPC** and deployed a **Windows Server 2022 EC2 instance** within the cloud network. The environment incorporated public and private subnets across multiple Availability Zones, routing components, internet connectivity, a NAT gateway, and security group controls. I also verified that the EC2 instance was running successfully and established an **RDP** session to the Windows server. This exercise gave me practical experience with cloud networking, VPC architecture, subnetting, routing, EC2 deployment, security groups, and remote administration in AWS.

---

## Screenshot

**Figure 1:** **Amazon VPC** configuration for `ACIVMLG-vpc` using the IPv4 CIDR block `172.16.0.0/16`, with the architecture preview showing the planned subnets and route tables.

<img width="1917" height="922" alt="01 – Configure an AWS Virtual Private Cloud and EC2 Instance" src="https://github.com/user-attachments/assets/e039a6b5-e2bc-46c9-806f-61b8727e1176" />

**Figure 2:** VPC architecture configured across two **Availability Zones** with two public subnets, two private subnets, and a NAT gateway.

<img width="1917" height="922" alt="02 – Configure an AWS Virtual Private Cloud and EC2 Instance" src="https://github.com/user-attachments/assets/85e92bb6-2f38-4b6f-903a-fccdd80b1243" />

**Figure 3:** Successful **VPC creation workflow** showing AWS provisioning the VPC and its associated networking resources, including subnets, route tables, an internet gateway, NAT gateway, and Elastic IP.

<img width="1918" height="922" alt="03 – Configure an AWS Virtual Private Cloud and EC2 Instance" src="https://github.com/user-attachments/assets/a42e1f38-a1e7-4c45-b253-dbf72f29a550" />

**Figure 4:** **Amazon EC2** network configuration showing the `ACIVMLG-vpc`, public subnet, automatic public IP assignment, key pair, and security group configuration for the Windows Server instance.

<img width="1918" height="922" alt="04 – Configure an AWS Virtual Private Cloud and EC2 Instance" src="https://github.com/user-attachments/assets/9c19fbbd-af74-46a2-bf1e-381e1f1c2916" />

**Figure 5:** **Amazon EC2** connection page showing the `ACIVMLG` instance running with both status checks passed and the **RDP** connection method available.

<img width="1918" height="921" alt="05 – Configure an AWS Virtual Private Cloud and EC2 Instance" src="https://github.com/user-attachments/assets/7d618b87-7f45-4d71-a403-815d30b679a9" />

**Figure 6:** Successful **Remote Desktop** session to the Windows Server EC2 instance, confirming that the cloud-hosted system was accessible and operational.

<img width="1918" height="933" alt="06 – Configure an AWS Virtual Private Cloud and EC2 Instance" src="https://github.com/user-attachments/assets/ba535fc1-6bd4-458a-9a0e-8aba8e7f07b0" />
