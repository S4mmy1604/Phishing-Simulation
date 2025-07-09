
# Phishing Simulation Using Kali Linux and SET

This repository contains a detailed lab simulation of a phishing attack using Kali Linux and the Social-Engineer Toolkit (SET). It demonstrates setting up a virtual lab environment, cloning legitimate websites, and capturing credentials using the Credential Harvester attack method.

---

## Table of Contents

- [Project Overview](#project-overview)  
- [Lab Environment Setup](#lab-environment-setup)  
- [Execution Steps](#execution-steps)  
- [Captured Output](#captured-output)  
- [Challenges and Resolutions](#challenges-and-resolutions)  
- [Report Generation](#report-generation)  
- [Disclaimer](#disclaimer)  

---

## Project Overview

This project simulates a real-world phishing attack in a controlled virtual environment. The Social-Engineer Toolkit's Credential Harvester method is used to clone websites and capture user credentials submitted via a fake login page.

---

## Lab Environment Setup

- **Kali Linux VM**  
  - Adapter 1: NAT (Internet access)  
  - Adapter 2: Host-Only (Communication with victim VM)  
  - IPs example: `10.0.2.x` (NAT), `192.168.56.150` (Host-Only)

- **Windows 10 VM** (Victim)  
  - Adapter 1: Host-Only  
  - IP example: `192.168.56.100`

- Network setup ensures Kali has internet access and can communicate locally with Windows VM.

---

## Execution Steps

1. Launch SET with:  
   ```bash
   sudo setoolkit
 2. Navigate menus:
   
  1) Social-Engineering Attacks  
  2) Website Attack Vectors  
  3) Credential Harvester Attack Method  
  2) Site Cloner
     

 3:  Enter Kali host-only IP address for POST back (e.g., 192.168.56.150).

4:  Enter target website URL to clone (examples:
    - https://github.com/login
    - https://phptravels.net/login)


5: Access cloned phishing page from Windows VM browser:
    http://192.168.56.150


6. Submit fake credentials and observe captured output in Kali terminal.

## Captured Output
Example output from SET after victim submits credentials:


[*] WE GOT A HIT! Printing the output:
PARAM: identifier=test@gmail.com
POSSIBLE PASSWORD FIELD FOUND: hiddenPassword=
Captured POST data is saved in reports directory.

## Challenges and Resolutions
Port 80 in use by Apache: Resolved by stopping Apache service (sudo systemctl stop apache2).

Blank phishing page due to missing internet on victim: Enabled NAT adapter on Windows VM.

Empty password fields due to JavaScript obfuscation: Limited by SET’s capabilities; advanced tools required for such sites.
