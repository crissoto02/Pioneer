# Pioneer
# Siemens KTP400 Basic – HMI Setup & Configuration

## 1. Project Overview

This project documents the setup and configuration of a Siemens KTP400 Basic HMI panel, used to interface with a Siemens S7-1200 PLC. The system is developed and configured using Siemens TIA Portal (version X.X).

## 2. Hardware Configuration

* **HMI model:** Siemens KTP400 Basic
* **PLC model:** Siemens S7-1200 (simulated using PLCSIM Advanced)
* **Power Supply:** 24V DC
* **Network:** PROFINET communication via Ethernet

## 3. Software Setup (TIA Portal)

* **TIA Portal Version:** X.X
* **New project creation:**

  * Add new devices: S7-1200 (virtual) and KTP400 Basic (physical)
  * Configure PROFINET communication between HMI and PLC
  * Set IP addresses (e.g., HMI: 192.168.0.2, PC virtual NIC: 192.168.0.100)
* **Tag synchronization:**

  * Link PLC tags to HMI by referencing PLC tags in HMI screens

## 4. HMI Screens

* **Startup screen:** Company logo, date/time, navigation buttons
* **Main screen:** System status indicators, control buttons (Start/Stop), process values display
* **Alarm screen:** Active and historical alarms display
* **Settings screen (optional):** Operator settings, language selection

## 5. PLC Logic Related to HMI

* **OB1 main program:** Includes basic logic for motor control, status feedback
* **Tags used by HMI:**

  * `Motor_Start` (Bool): Triggered from HMI
  * `Motor_Status` (Bool): Feedback from PLC
  * `Temp_Value` (Real): Displayed on HMI

## 6. Testing and Simulation

* **Simulated PLC:** PLCSIM Advanced used to simulate S7-1200
* **Ethernet setup:**

  * HMI connected via Ethernet to PC's virtual network adapter
  * IP address of virtual NIC: 192.168.0.100
  * HMI IP address: 192.168.0.2
* **Enable external communication** in PLCSIM Advanced
* **Download:**

  * PLC program to PLCSIM Advanced
  * HMI runtime to physical KTP400 Basic
* **Results:**

  * Verified real HMI buttons trigger virtual PLC logic
  * Tags and values reflected correctly

## 7. Notes & Best Practices

* Always compile and download the full project after major changes.
* Use consistent naming for tags.
* Back up the project before deployment.
* Validate IP settings and PROFINET configuration on both devices.
* For this method, ensure PLCSIM Advanced is installed and configured to allow external connections.

## 8. Change Log

* **2025-07-07:** Initial setup completed. Connected HMI to simulated PLC using PLCSIM Advanced.
* **2025-07-08:**&#x20;
* **2025-07-09:**&#x20;

---

> *Maintained by the automation team. Contributions welcome.*
