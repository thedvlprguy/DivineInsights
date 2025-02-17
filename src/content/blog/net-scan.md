---
title: How to Build Netscan
author: Aditya Tomar
pubDatetime: 2025-02-17T15:22:00Z
slug: how-to-build-netscan
featured: true
draft: false
tags:
    - cybersecurity
    - threat-intelligence
    - network-scanner
    - leakcheck
ogImage: ""
description: A guide to building the Netscan Cyber Threat Intelligence Dashboard, featuring network scanning, OSINT, exploit scanning, and LeakCheck API integration.
---

# How to Build Netscan

This document provides a structured breakdown of how to build the **Netscan Cyber Threat Intelligence Dashboard**, focusing on network scanning, OSINT, exploit scanning, and real-time threat monitoring for cybersecurity.

## Project Overview
- **What is Netscan?**: A mobile app that collects and visualizes cybersecurity threats, including phishing, dark web monitoring, OSINT data, and data breaches from the LeakCheck API.
- **Why Netscan?**: A comprehensive, real-time dashboard that helps monitor cybersecurity risks in military networks and critical infrastructures.

## Setup & Installation
### 1. **Clone the Repository**
Start by cloning the repository to your local machine:
```bash
git clone https://github.com/thedvlprguy/netscan.git
```

### 2. **Install Frontend Dependencies (React Native + Expo)**
Navigate to the project folder and install the necessary dependencies:
```bash
cd netscan
npm install
```

### 3. **Run the Frontend**
Run the app using Expo CLI:
```bash
expo start
```
This will open the Expo development environment in your browser. You can scan the QR code to test the app on your mobile device.

## Backend Setup (Python + FastAPI/Flask)
### 1. **Install Backend Dependencies**
The backend uses **Python** with **FastAPI** (or **Flask**) for ML and API interactions. Install the dependencies:
```bash
pip install -r requirements.txt
```

### 2. **Run the Backend Server**
To run the backend, use:
```bash
uvicorn main:app --reload  # For FastAPI
```
For Flask, use:
```bash
python app.py
```
This will start the server and allow communication with the mobile app.

## APIs Configuration
### 1. **OSINT APIs**
Integrated into the backend for fetching intelligence data on domains, IP addresses, and threats.

### 2. **Shodan API**
Used for monitoring vulnerabilities in public-facing systems. Make sure to configure your API keys.

### 3. **Nmap**
Configured to scan local networks for vulnerabilities, services, and devices.

### 4. **LeakCheck API**
The **LeakCheck API** is integrated into Netscan for identifying potential data breaches. This API checks whether an email or username has been exposed in any known data breaches. You can use this API to monitor and alert users about compromised credentials.

Make sure to configure your **LeakCheck API** keys and integrate it into the backend to check for breach incidents and notify users accordingly.

## Frontend & Backend Integration
- The mobile app communicates with the backend in real-time, pulling data from the APIs for displaying threat information, network vulnerabilities, and other security insights.

## Key Features of Netscan
1. **Network Scanning**: Discover devices and open ports in local networks.
2. **OSINT Data**: Collect and display real-time threat intelligence.
3. **Exploit Scanner**: Monitor and identify known vulnerabilities in services and devices.
4. **LeakCheck Integration**: Identify potential breaches for users’ credentials and notify them immediately.

## Contributing to Netscan
We welcome contributions to **Netscan**! If you want to contribute, follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to your branch (`git push origin feature/your-feature`).
5. Open a Pull Request with a detailed description of your changes.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
