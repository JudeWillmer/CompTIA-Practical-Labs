# Installation of Peripheral Devices

## Overview

This lab covers the practical tasks I completed to install and manage **peripheral devices** within Windows environments. I used **Device Manager** to manually install and inspect device drivers, reviewed driver properties and Plug and Play behaviour, configured both **local and network printers**, and set up **Windows Print and Document Services** on a server. I also connected a Windows 11 workstation to a shared printer and verified the printer through **Print Management** and **IIS Internet Printing**, giving me practical experience with device installation, driver management, print services, and network-based peripheral access.

---

# Exercise 1 - Installing Device Drivers

## Objective

Install and manage hardware devices using **Windows Device Manager**, including manually adding a network adapter, inspecting device driver information, and demonstrating how Windows **Plug and Play** can automatically detect and restore hardware.

---

## Implementation

I used **Windows Device Manager** on the Windows 11 workstation to manually install a **Microsoft KM-TEST Loopback Adapter**. Using the Add Hardware Wizard, I selected the network adapter hardware category and installed the Microsoft loopback adapter, allowing me to practise adding hardware that was not automatically detected by the operating system.

After installation, I reviewed the properties of the **Microsoft KM-TEST Loopback Adapter** and examined its driver information. I used **Driver File Details** to identify the associated Windows driver file and verify information including the driver provider and digital signer.

I then tested Windows **Plug and Play** hardware detection by uninstalling the **Intel(R) 82574L Gigabit Network Connection** from Device Manager. After scanning for hardware changes, Windows automatically detected the network adapter and restored it, demonstrating how the operating system can identify supported hardware and reinstall the required device configuration.

---

## Navigation

```text
Device Manager
  ↳ Action
      ↳ Add Legacy Hardware
          ↳ Manually Select Hardware
              ↳ Network Adapters
                  ↳ Microsoft
                      ↳ Microsoft KM-TEST Loopback Adapter
                          ↳ Install Device

Device Manager
  ↳ Network Adapters
      ↳ Microsoft KM-TEST Loopback Adapter
          ↳ Properties
              ↳ Driver
                  ↳ Driver Details

Device Manager
  ↳ Network Adapters
      ↳ Intel(R) 82574L Gigabit Network Connection
          ↳ Uninstall Device

Device Manager
  ↳ Scan for Hardware Changes
      ↳ Verify Intel(R) 82574L Gigabit Network Connection Restored
```

---

## Outcome

I successfully installed and managed network devices using **Windows Device Manager**, including manually adding the **Microsoft KM-TEST Loopback Adapter** and reviewing its associated driver information. I also demonstrated Windows **Plug and Play** functionality by uninstalling the Intel network adapter and using a hardware scan to automatically detect and restore the device. This exercise gave me practical experience with hardware installation, device drivers, driver file inspection, Device Manager, and automatic hardware detection in Windows.

---

## Screenshot

**Figure 1:** Windows **Device Manager** displaying the successfully installed **Microsoft KM-TEST Loopback Adapter** alongside the existing Intel network adapter, confirming that the manually selected device was added to the system.

[SCREENSHOT 1]

**Figure 2:** **Driver File Details** for the Microsoft KM-TEST Loopback Adapter displaying the associated Windows driver file, provider information, and **Microsoft Windows** digital signer.

[SCREENSHOT 2]

**Figure 3:** Windows **Device Manager** displaying the restored **Intel(R) 82574L Gigabit Network Connection** after scanning for hardware changes, demonstrating automatic device detection and restoration through Windows **Plug and Play**.

[SCREENSHOT 3]

---
