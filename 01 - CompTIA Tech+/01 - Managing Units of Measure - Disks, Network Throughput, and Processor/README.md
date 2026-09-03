# Managing Units of Measure - Disks, Network Throughput, and Processor

## Overview

This lab covers the practical tasks I completed to explore how different **units of measurement** are used across computer systems. I used **Windows Disk Management** to create and manage disk volumes and a virtual hard disk, captured network traffic with **Wireshark** to examine network throughput, and used **CPU-Z** alongside Windows system information to review processor specifications. These tasks gave me practical experience working with **storage capacity**, **network data rates**, and **processor performance** using common Windows administration and diagnostic tools.

---

# Exercise 1 - Create Disk Volumes of Different Sizes

## Objective

Create and manage disk volumes of different sizes using **Windows Disk Management**, including shrinking an existing partition, creating and formatting new **NTFS volumes**, and configuring a **virtual hard disk** to demonstrate storage capacities measured in megabytes, gigabytes, and terabytes.

---

## Implementation

I used **Windows Disk Management** to manage the storage configuration of the Windows 11 workstation. I first reduced the size of the existing **C:** volume by 2,000 MB, creating approximately **1.95 GB of unallocated space** that could be used for additional partitions.

Using the available disk space, I created a **500 MB NTFS volume** named **Megabyte Unit Storage (E:)** and a **1 GB NTFS volume** named **Gigabyte Unit Storage (F:)**. This allowed me to work with different storage capacities and practise creating, formatting, labelling, and assigning drive letters to Windows volumes.

I then used Disk Management to create a **10 TB VHDX virtual hard disk** and configured it as **dynamically expanding**. After creating and preparing the virtual disk, I created an NTFS volume named **Terabyte (V:)** and verified that the new storage volumes were available through **File Explorer**.

---

## Navigation

```text
Disk Management
  ↳ C:
      ↳ Shrink Volume
          ↳ Shrink by 2,000 MB

Disk Management
  ↳ Unallocated Space
      ↳ New Simple Volume
          ↳ 500 MB → E: → NTFS → Megabyte Unit Storage
          ↳ 1 GB → F: → NTFS → Gigabyte Unit Storage

Disk Management
  ↳ Action
      ↳ Create VHD
          ↳ 10 TB
          ↳ VHDX
          ↳ Dynamically Expanding
              ↳ Initialise Disk
                  ↳ New Simple Volume
                      ↳ V: → NTFS → Terabyte

File Explorer
  ↳ This PC
      ↳ Verify E:, F:, and V:
```

---

## Outcome

I successfully created and managed storage volumes using **Windows Disk Management**, starting by shrinking the existing C: partition and using the resulting unallocated space to create separate **500 MB** and **1 GB NTFS volumes**. I also created a **10 TB dynamically expanding VHDX**, configured it as the **Terabyte (V:)** volume, and verified that all three new drives were accessible through File Explorer. This exercise gave me practical experience working with disk partitions, filesystems, drive letters, virtual disks, and storage capacities measured across **MB, GB, and TB**.

---

## Screenshot

**Figure 1:** Windows **Disk Management** displaying approximately **1.95 GB of unallocated space** after shrinking the C: volume by 2,000 MB.

<img width="1917" height="927" alt="01 – Create Disk Volumes of Different Sizes" src="https://github.com/user-attachments/assets/d9ff4ccb-6708-4acb-8bf0-29a297383118" />

**Figure 2:** Windows **Disk Management** displaying the completed **Megabyte Unit Storage (E:)** 500 MB NTFS volume and **Gigabyte Unit Storage (F:)** 1 GB NTFS volume.

<img width="1918" height="928" alt="02 – Create Disk Volumes of Different Sizes" src="https://github.com/user-attachments/assets/39205cd9-0e30-4ae2-a255-401dbd0ad3b4" />

**Figure 3:** **Create and Attach Virtual Hard Disk** configuration showing a **10 TB VHDX** configured as a **dynamically expanding** virtual hard disk.

<img width="1918" height="928" alt="03 – Create Disk Volumes of Different Sizes" src="https://github.com/user-attachments/assets/f77d6639-b63e-4271-b033-65138a9b21ce" />

**Figure 4:** Windows **File Explorer** displaying the completed **Megabyte Unit Storage (E:)**, **Gigabyte Unit Storage (F:)**, and **Terabyte (V:)** volumes, confirming that the newly configured storage is available to the operating system.

<img width="1917" height="926" alt="04 – Create Disk Volumes of Different Sizes" src="https://github.com/user-attachments/assets/17ba52bb-33fa-4321-ac31-a630df648545" />
