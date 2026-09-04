# Installation of Peripheral Devices

## Overview

This lab covers the practical tasks I completed to install and manage **peripheral devices** within Windows environments. I used **Device Manager** to manually install and inspect device drivers, reviewed driver properties and **Plug and Play** behaviour, configured both **local and network printers**, and implemented **Windows Print and Document Services** on a server. I also connected a Windows 11 workstation to a shared printer and verified the printer through **Print Management** and **IIS Internet Printing**, giving me practical experience with device installation, driver management, print services, and network-based peripheral access.

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

<img width="1918" height="927" alt="01 – Installing Device Drivers" src="https://github.com/user-attachments/assets/ff14a0fa-571c-4470-b26d-933d4bbec53d" />

**Figure 2:** **Driver File Details** for the Microsoft KM-TEST Loopback Adapter displaying the associated Windows driver file, provider information, and **Microsoft Windows** digital signer.

<img width="1917" height="930" alt="02 – Installing Device Drivers" src="https://github.com/user-attachments/assets/2537d82f-279e-4567-b746-f165f73b5ca1" />

**Figure 3:** Windows **Device Manager** displaying the restored **Intel(R) 82574L Gigabit Network Connection** after scanning for hardware changes, demonstrating automatic device detection and restoration through Windows **Plug and Play**.

<img width="1918" height="926" alt="03 – Installing Device Drivers" src="https://github.com/user-attachments/assets/874107d7-a062-45fa-a40c-02246709d429" />

# Exercise 2 - Manage Windows Printing Services

## Objective

Install and configure local and network printers across Windows 11 and Windows Server, set up **Windows Print and Document Services**, manage shared printers through **Print Management**, connect a Windows 11 workstation to a server-hosted printer, and verify access through **IIS Internet Printing**.

---

## Implementation

I first configured printer functionality within the Windows environment by installing the **Microsoft MS-XPS Class Driver 2** and working with printer sharing. On the Windows Server, I then configured a network printer using a **Standard TCP/IP Port** with the IP address `192.168.0.1` and shared the printer as **Printer1** so that it could be accessed by network clients.

I used **Server Manager** on `ACIDC01` to install **Print and Document Services** and enabled the **Print Server**, **Internet Printing**, and **LPD Service** role services. This provided the server-side components required to centrally host and manage network printing services.

After configuring the server roles, I used **Print Management** to verify the printers hosted on `ACIDC01` and review their queue status, driver information, and configuration. I then connected the Windows 11 workstation to the shared printer hosted on the server and confirmed that the network printer was successfully available to the client.

Finally, I accessed the server's **IIS Internet Printing** interface from the Windows 11 workstation and verified that the shared printer was listed with a **Ready** status, confirming that the web-based printing interface was operational within the lab environment.

---

## Navigation

```text
Windows 11
  ↳ Settings
    ↳ Bluetooth & devices
      ↳ Printers & scanners
        ↳ Add device manually
          ↳ Install Local Printer

Windows Server
  ↳ Printers & scanners
    ↳ Add device manually
      ↳ Standard TCP/IP Port
        ↳ 192.168.0.1
          ↳ Share as Printer1

Server Manager
  ↳ Add Roles and Features
    ↳ Print and Document Services
      ↳ Print Server
      ↳ Internet Printing
      ↳ LPD Service

Server Manager
  ↳ Tools
    ↳ Print Management
      ↳ Print Servers
        ↳ ACIDC01
          ↳ Printers

Windows 11
  ↳ Printers & scanners
    ↳ Add device manually
      ↳ Shared Printer
        ↳ \\ACIDC01\Printer1

Microsoft Edge
  ↳ http://acidc01/printers/
    ↳ Verify Shared Printer Ready
```

---

## Outcome

I successfully configured and managed printing services across Windows 11 and Windows Server, including local printer installation, TCP/IP printer configuration, printer sharing, and centralised print server administration. I also connected a Windows 11 workstation to a printer hosted on `ACIDC01` and verified the printer through both **Print Management** and **IIS Internet Printing**. This exercise gave me practical experience with Windows print services, network printer deployment, shared peripheral access, and server-based printer management.

---

## Screenshot

**Figure 1:** Network printer configuration on `ACIDC01` using a **Standard TCP/IP Port** with the IP address `192.168.0.1`.

**Figure 2:** **Print and Document Services** role configuration showing **Print Server**, **Internet Printing**, and **LPD Service** enabled on `ACIDC01`.

**Figure 3:** **Print Management** displaying the printers hosted on `ACIDC01`, including queue status, driver version, and driver type.

**Figure 4:** Windows 11 confirming that the shared **Microsoft MS-XPS Class Driver 2** printer hosted on `ACIDC01` was successfully added.

**Figure 5:** Windows 11 **Printers & scanners** displaying the server-hosted printer alongside the locally installed printers.

**Figure 6:** **IIS Internet Printing** interface on `ACIDC01` displaying the shared printer with a **Ready** status.
