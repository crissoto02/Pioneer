# Pioneer
# Siemens KTP400 Basic – HMI Setup & Configuration

## 1. Project Overview

This project documents the setup and configuration of a Siemens KTP400 Basic HMI panel, used to interface with a Siemens S7-1200 PLC. The system is developed and configured using Siemens TIA Portal (version X.X).

## 2. Hardware Configuration

* **HMI model:** Siemens KTP400 Basic
* **PLC model:** Siemens S7-1200 (exact model TBD)
* **Power Supply:** 24V DC
* **Network:** PROFINET communication via Ethernet

## 3. Software Setup (TIA Portal)

* **TIA Portal Version:** X.X
* **New project creation:**

  * Add new devices: S7-1200 and KTP400 Basic
  * Configure PROFINET communication between HMI and PLC
  * Set IP addresses (e.g., HMI: 192.168.0.2, PLC: 192.168.0.1)
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

* **Offline HMI simulation:** Tested navigation and button interaction
* **Online test with PLC:** Verified tag communication and screen response
* **Common issues:**

  * Tag not linked correctly → Rechecked HMI-PLC connection
  * Screen elements not updating → Verified runtime updates

## 7. Notes & Best Practices

* Always compile and download the full project after major changes.
* Use consistent naming for tags.
* Back up the project before deployment.
* Validate IP settings and PROFINET configuration on both devices.

## 8. Change Log

* **2025-07-07:** Initial setup completed. Connected HMI to PLC.
* **2025-07-08:** Designed basic HMI screens. Integrated motor control buttons.
* **2025-07-09:** Added alarm screen and historical logging.

---

> *Maintained by the automation team. Contributions welcome.*
