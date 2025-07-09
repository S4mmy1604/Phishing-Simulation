
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
