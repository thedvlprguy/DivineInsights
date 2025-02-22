---
title: How to Build WebMap
author: Sabyasachi Rana
pubDatetime: 2025-02-22T15:22:00Z
slug: how-to-use-webmap
featured: true
draft: false
tags:
    - cybersecurity
    - network-scanner
    - nmap
    - vulnerability-assessment
ogImage: ""
description: A guide to setting up WebMap, a dashboard for visualizing and analyzing Nmap scan results with ease, including CVE and exploit information.
---

# How to Build WebMap

This document will guide you through setting up **WebMap**, a powerful dashboard for viewing and managing Nmap scan results. WebMap integrates with the **Nmap XML Reports** to provide an easy-to-use interface for managing scanned network data, discovering vulnerabilities, and identifying exploits.

## Project Overview
- **What is WebMap?**: WebMap is a web-based tool that allows users to visualize Nmap XML reports, analyze vulnerabilities, and interact with various scanning results. It integrates with external APIs, like the CVE and Exploit databases, to give a comprehensive view of scanned hosts and their vulnerabilities.
- **Why WebMap?**: WebMap makes it easy to manage and analyze Nmap scan results with graphical charts, labels, notes, and exploit information, all accessible via a clean web interface. This is especially useful for network administrators, penetration testers, and security researchers who perform regular Nmap scans.

## Setup & Installation

### 1. **Download WebMap with Docker**
To start using WebMap, you can quickly deploy it using Docker. First, create a directory for your WebMap data:
```bash
mkdir /tmp/webmap
```

Then, run the following command to start the WebMap container:
```bash
docker run -d \
         --name webmap \
         -h webmap \
         -p 8000:8000 \
         -v /tmp/webmap:/opt/xml \
         reborntc/webmap
```
This will download the WebMap Docker image and start the container.

### 2. **Run Nmap Scan and Save the Results**
You can now run your Nmap scan and save the results as an XML file in the `/tmp/webmap` directory:
```bash
nmap -sT -A -T4 -oX /tmp/webmap/myscan.xml 192.168.1.0/24
```
This will scan the network `192.168.1.0/24` and save the scan results as `myscan.xml` in the `/tmp/webmap` folder.

### 3. **Access WebMap Dashboard**
Open your browser and go to `http://localhost:8000` to access the WebMap dashboard. Here, you will be able to view, analyze, and manage the scan results.

### 4. **Generate New Token for Access**
To access the WebMap dashboard, you need an API token. You can generate a new token with this command:
```bash
docker exec -ti webmap /root/token
```

## Backend Setup (Nmap Integration)
WebMap works with **Nmap** XML reports to provide detailed insights into scanned networks, hosts, and vulnerabilities.

### 1. **Run Nmap Scan and Collect CVE and Exploits**
WebMap integrates with **circl.lu**'s API to provide CVE and exploit information for the CPE (Common Platform Enumeration) of discovered services. Only specific versions of services are checked (e.g., `cpe:/a:microsoft:iis:7.5`). 

### 2. **Network View**
WebMap has an enhanced **Network View**, which gives a graphical representation of the network layout. This helps users visualize the structure and connections between devices within their network.

## API & Feature Configuration

### 1. **WebMap RESTful API**
WebMap also exposes a **RESTful API** from version v2.1 onwards. With the API, users can query scan files and retrieve detailed information. For example:
```bash
curl -s 'http://localhost:8000/api/v1/scan?token=<token>'
```
This will return a list of scan results. You can get detailed information about a specific scan or host by appending the scan or host details to the URL.

### 2. **Scan Statistics and Charts**
WebMap provides statistics and charts for discovered services, ports, operating systems, and more. These charts are automatically generated and displayed in the dashboard for quick analysis.

### 3. **Generate PDF Reports**
WebMap allows you to generate **PDF reports** that include charts, details, labels, and notes, making it easy to share scan results with others. It also formats the report title based on the filename of the Nmap XML, replacing underscores with spaces and removing the `.xml` extension.

### 4. **Search for CVEs and Exploits**
WebMap provides functionality to search for CVEs and exploits based on the CPEs discovered in your Nmap scan. This integration helps identify known vulnerabilities that could affect your network.

## Key Features of WebMap
1. **Import and Parse Nmap XML Files**: Easily import and view Nmap XML scan results.
2. **Run and Schedule Nmap Scans**: Schedule and run Nmap scans directly from the dashboard.
3. **Statistics and Charts**: Visualize discovered services, ports, OS types, and more.
4. **Inspect Hosts**: Click on a host IP to view detailed information, including CVEs, exploits, and vulnerabilities.
5. **Label and Add Notes to Hosts**: Add labels and notes to specific hosts for better organization and tracking.
6. **PDF Report Generation**: Generate detailed PDF reports of your scans.
7. **Clipboard Commands**: Copy Nikto, Curl, or Telnet commands to clipboard.
8. **CVE & Exploit Search**: Search for CVEs and exploits based on Nmap's CPE data.
9. **RESTful API**: Query scan results programmatically.

## Contributing to WebMap
We welcome contributions to **WebMap**! If you would like to contribute, follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to your branch (`git push origin feature/your-feature`).
5. Open a Pull Request with a detailed description of your changes.

## License
This project is licensed under the GPL-2.0 License. See the [LICENSE](LICENSE) file for details.

---

This guide walks you through setting up WebMap using Docker to manage your Nmap scans and visualize vulnerabilities. With its easy-to-use interface, API integration, and powerful scanning tools, WebMap is an essential tool for network security professionals.
