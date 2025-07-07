# Pioneer
# Siemens KTP400 Basic – HMI Setup & Configuration

## Module 1: HMI Wiring

This module covers the physical wiring and powering of the Siemens KTP400 Basic HMI panel.

### Power Supply Setup

* **Power source used:** Meanwell LRS-50-24 (24 V DC output)
* **Terminals connected:**

  * **+V (Meanwell)** → **L+ (HMI)**
  * **–V (Meanwell)** → **M (HMI)**
* **AC Input to power supply:**

  * **L:** Connected to AC phase (110/220 V)
  * **N (M):** Connected to AC neutral
  * **⏚ GND:** Connected to system ground (Not used in this project setup but recommended)

### Ferrule Usage

* Used **insulated ferrules** to crimp wire ends before inserting into HMI terminals
* Ensured:

  * No copper strands exposed outside the ferrule
  * Only the plastic insulation of the ferrule is visible at the terminal entrance
  * No part of the ferrule’s metal body protrudes excessively from the terminal

### HMI Power-On Verification

* Panel successfully powered on using the Meanwell LRS-50-24

## 1. Project Overview

This project documents the setup and configuration of a Siemens KTP400 Basic HMI panel, used to interface with a Siemens S7-1200 PLC (S7 series are mostlikely to be compatible). The system is developed and configured using Siemens TIA Portal (version 19).

## 2. Hardware Configuration

* **HMI model:** Siemens KTP400 Basic
* **PLC model:** Siemens S7-1200 (simulated using PLCSIM Advanced)
* **Power Supply:** 24V DC (required for HMI operation)
* **Network:** PROFINET communication via Ethernet

> ⚠️ Note: The HMI panel must be powered with a stable 24V DC supply in addition to the Ethernet communication. Ethernet provides data communication only, not power.

## 3. Software Setup (TIA Portal)

* **TIA Portal Version:** V19
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
* The KTP400 Basic HMI **requires a 24V DC power supply** to operate; Ethernet alone is not sufficient.

## 8. Change Log

* **2025-07-07:** Initial setup completed. Connected HMI to simulated PLC using PLCSIM Advanced.
* **2025-07-08:**
* **2025-07-09:**

---

> *Maintained by the automation team. Contributions welcome.*
