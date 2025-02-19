---
title: How To Use Nmap
author: Aditya Tomar
pubDatetime: 2025-02-20T10:00:00Z
slug: nmap-notes
featured: true
draft: false
tags:
    - cybersecurity
    - network-scanner
    - nmap
ogImage: ""
description: A comprehensive guide to various Nmap commands and their functionalities for network scanning and analysis.
---

# Nmap Usage Notes

This document provides a structured overview of various Nmap commands, detailing their usage, functionality, and insights.

## 1️⃣ Aggressive Scan (-A)

Try it:

```bash
nmap -v -A scanme.nmap.org
```

### How It Works:
- **Host Discovery**: Checks if the host is alive.
- **-v**: Provides detailed output (verbose).
- **OS Detection**: Uses TCP/IP fingerprinting to guess the OS.
- **Version Detection**: Identifies running services and their versions.
- **Script Scanning**: Uses Nmap’s scripting engine (NSE) to find vulnerabilities.
- **Traceroute**: Shows the path packets take to reach the target.

### Example Output (Shortened):
```
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.12s latency).
Not shown: 994 closed ports
PORT      STATE SERVICE VERSION
22/tcp    open  ssh     OpenSSH 6.6.1p1 Ubuntu
80/tcp    open  http    Apache httpd 2.4.7
```

### 🔍 Insight:
Reveals open ports, services, OS, and traceroute for the target.

## 2️⃣ Ping Sweep (-sn)

Try it (LAN Discovery):

```bash
nmap -v -sn 192.168.1.0/24
```

(Replace with your actual subnet if needed)

### How It Works:
- **No Port Scan**: Just finds alive hosts on a network.
- **Sends ICMP Echo Requests** (ping).
- **Uses ARP requests** on local networks for better accuracy.

### Example Output (Shortened):
```
Nmap scan report for 192.168.1.1 (Router)
Host is up (0.0012s latency).
Nmap scan report for 192.168.1.100 (Laptop)
Host is up (0.0009s latency).
```

### 🔍 Insight:
Great for finding all devices connected to a network without scanning ports.

## 3️⃣ Random IP Scan (-iR)

Try it (Caution: Random Public IPs!)

```bash
nmap -v -iR 10 -Pn -p 80
```

(Scans 10 random IPs for open HTTP servers)

### How It Works:
- **-iR 10**: Picks 10 random public IPs.
- **-Pn**: Assumes all hosts are up (skips ping).
- **-p 80**: Only scans port 80 (HTTP).

### Example Output (Shortened):
```
Nmap scan report for 192.168.1.10
Host is up.
PORT   STATE SERVICE
80/tcp open  http
```

### 🔍 Insight:
Useful for finding web servers worldwide, but it can trigger firewall alerts if misused!

## 🔹 Summary Table

| Command                              | Purpose                                               | Key Flags      |
|--------------------------------------|------------------------------------------------------|----------------|
| `nmap -v -A scanme.nmap.org`        | Aggressive scan with OS, services, scripts, traceroute | -A, -v         |
| `nmap -v -sn 192.168.0.0/16`        | Find live hosts without scanning ports               | -sn, -v        |
| `nmap -v -iR 10 -Pn -p 80`          | Scan 10 random IPs for open port 80                  | -iR, -Pn, -p   |

## Nmap Scan Report for iichevit.com

### Overview
This report summarizes the results of an Nmap scan conducted on the domain iichevit.com. The scan was performed using Nmap version 7.80 and provides insights into the open ports and services running on the host.

### Scan Details
- **Target**: iichevit.com
- **IP Address**: 76.76.21.21
- **Scan Start Time**: 2025-02-19 22:14 IST
- **Latency**: 0.0096 seconds

### Scan Results
- **Host Status**: Up
- **Filtered Ports**: Not shown: 998 filtered ports
- **Open Ports**:
  - **80/tcp**: open (http)
  - **443/tcp**: open (https)

### Explanation of Scanning 1000 Ports
Nmap, by default, scans the 1,000 most common ports for both TCP and UDP protocols. This selection is based on the following considerations:
- **Efficiency**: Scanning all 65,535 ports can be time-consuming. Focusing on the most commonly used ports provides quick and relevant results.
- **Common Services**: Default ports cover the majority of popular services, allowing users to quickly identify essential services without unnecessary delays.
- **User Needs**: Most users are primarily interested in common services likely running on a target host.

### Open Ports Identified
In this scan, two ports were found to be open:
- **Port 80 (HTTP)**: Typically used for web traffic, indicating that the host is serving web pages.
- **Port 443 (HTTPS)**: Used for secure web traffic, indicating that the host supports encrypted connections.

### Conclusion
The Nmap scan of iichevit.com successfully identified two open ports, providing insight into the services available on the host. For a more comprehensive analysis, users can perform additional scans targeting specific ports or all ports as needed.

## Nmap Command Explanation

The command `nmap -oG - 172.17.37.0-255 -vv > Result` performs a network scan with specific options. Here’s a breakdown:

- **Nmap**: A powerful network scanning tool used to discover hosts and services on a network.
- **-oG -**: Output Format: Specifies that the output should be in "grepable" format, which is useful for further processing.
- **172.17.37.0-255**: Target Range: Specifies the range of IP addresses to scan.
- **-vv**: Verbose Mode: Increases verbosity, providing more detailed output about the scan process and results.
- **> Result**: Output Redirection: The results of the scan are redirected to a file named Result.

### Summary
- **Purpose**: To scan a specific range of IP addresses and save detailed results in a grepable format for later analysis.
- **Use Case**: Useful for network administrators to identify active hosts and services within a specified range.

## Nmap Command Explanation

The command `nmap -oG - 172.17.37.0-255 -p 22 -vv > Resulti` performs a targeted network scan with specific options. Here’s a breakdown:

- **Nmap**: A network scanning tool used to discover hosts and services.
- **-oG -**: Output Format: Specifies that the output should be in "grepable" format for easy parsing.
- **172.17.37.0-255**: Target Range: Specifies the range of IP addresses to scan.
- **-p 22**: Port Specification: Tells Nmap to scan only port 22 (SSH).
- **-vv**: Verbose Mode: Increases verbosity, providing more detailed output about the scan process and results.
- **> Resulti**: Output Redirection: The results of the scan are saved to a file named Resulti.

### Summary
- **Purpose**: To scan a specific range of IP addresses for open SSH ports (port 22) and save detailed results in a grepable format for later analysis.

## Nmap Aggressive Scan Overview

The command `nmap -A scanme.nmap.org` performs an aggressive scan on the target scanme.nmap.org. Here’s a concise breakdown:

- **Nmap**: A powerful network scanning tool used for discovering hosts and services.
- **-A Option**: Aggressive Scan: Enables several advanced features, including:
  - **OS Detection**: Identifies the operating system of the target.
  - **Version Detection**: Determines the version of the services running on open ports.
  - **Script Scanning**: Executes Nmap scripts to gather more information about the target.
  - **Traceroute**: Maps the path packets take to reach the target.
- **Target**: scanme.nmap.org: A public Nmap testing server provided for educational and testing purposes.

### Summary
- **Purpose**: To perform a comprehensive scan that identifies the operating system, service versions, and other details about the target, providing a thorough analysis of the host's network services.

## Nmap Fast Scan Overview

The command `nmap -F scanme.nmap.org` executes a fast scan on the target scanme.nmap.org. Here’s a brief breakdown:

- **Nmap**: A widely-used network scanning tool for discovering hosts and services.
- **-F Option**: Fast Scan: Enables a quicker scan by limiting the number of ports scanned to the 1,000 most common ports.

### Summary
- **Purpose**: To quickly identify open ports and services on the target by scanning only the most common ports, making it suitable for rapid assessments.

## Nmap Fast Scan for Multiple Targets

The command `nmap -F schemcon2024.com schemcon2025.com > schemcon` performs a fast scan on two specified domains. Here’s a concise breakdown:

- **Nmap**: A powerful network scanning tool used to discover hosts and services.
- **-F Option**: Fast Scan: Limits the scan to the 1,000 most common ports.
- **Targets**: schemcon2024.com and schemcon2025.com: The two domains being scanned for open ports and services.
- **Output Redirection**: > schemcon: The results of the scan are saved to a file named schemcon for later review.

### Summary
- **Purpose**: To quickly scan the specified domains for open ports using a fast scan, with results saved to a designated file for easy access.

## Nmap Open Ports Scan

The command `nmap --open www.github.com` performs a scan to identify open ports on the specified target. Here’s a brief breakdown:

- **Nmap**: A widely-used network scanning tool for discovering hosts and services.
- **--open Option**: Filter for Open Ports: This option instructs Nmap to display only the ports that are open.
- **Target**: www.github.com: The specific domain being scanned for open ports.

### Summary
- **Purpose**: To check for open ports on GitHub's server, providing a focused view of accessible services without clutter from closed ports.

## Nmap Aggressive Scan with Timing

The command `nmap -T4 -A -v scanme.nmap.org` performs an aggressive scan with a specified timing template. Here’s a concise breakdown:

- **Nmap**: A powerful network scanning tool used for discovering hosts and services.
- **-T4 Option**: Timing Template: Sets the timing to "Aggressive," which speeds up the scan by reducing wait times between probes.
- **-A Option**: Aggressive Scan: Enables OS detection, version detection, script scanning, and traceroute.
- **-v Option**: Verbose Mode: Increases the verbosity of the output.

### Summary
- **Purpose**: To perform a fast and comprehensive scan that identifies the operating system, service versions, and other details about the target, with detailed output for better analysis.
