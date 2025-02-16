---
author: Aditya Tomar
pubDatetime: 2022-09-23T15:22:00Z
modDatetime: 2023-12-21T09:12:47.400Z
title: Creating a Port Scanner in Python
slug: creating-a-port-scanner-in-python
featured: true
draft: false
tags:
  - cybersecurity
  - python
  - penetration-testing
description:
  A step-by-step guide to building a custom port scanner in Python for penetration testing and security assessment.
---

## Introduction

Port Scanners are primarily used for Penetration Testing and Information Gathering. Essentially, we are looking for open ports in a host for one of two reasons: to ensure our servers are secure or to exploit those of someone else. An unnecessarily opened port means vulnerability and comes with a lack of security.

Therefore, it is reasonable to scan the ports of your own network in order to spot potential security gaps. To do so, we can use a popular and professional open-source software like Nmap. However, in this tutorial, we will code our own port scanner in Python. This approach allows us to customize the scanner as we want while learning about programming. Python is chosen for its simplicity, modernity, and power.

Before we start, you need to know that port scanning someone else’s network without their permission is a crime. Only scan your own network or one that you are permitted to. Alternatively, you might use scanme.nmap.org to experiment. I do not take any responsibility for the misuse of this information.

## Basic Functionality

A port scanner tries to connect to an IP address on a specific port. Typically, when we browse the web, we connect to servers via port 80 (HTTP) or port 443 (HTTPS). However, there are many other crucial ports, such as:

- 21 (FTP)
- 22 (SSH)
- 25 (SMTP)
- and many more.

There are over 130,000 ports, of which 1,023 are standardized and 48,128 reserved. When building a port scanner, efficiency is key, so we focus on crucial ports.

### Simple Port Scanner in Python

```python
def portscan(port):
    try:
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.connect((target, port))
        return True
    except:
        return False
```

This function creates a socket that attempts to connect to a target on a specific port. If successful, it returns `True`; otherwise, `False`. We can then loop through a range of ports:

```python
for port in range(1, 1024):
    result = portscan(port)
    if result:
        print("Port {} is open!".format(port))
    else:
        print("Port {} is closed!".format(port))
```

This method is functional but slow since it scans ports sequentially. To improve speed, we use multithreading.

## Preparing the Ports

### Required Libraries

```python
from queue import Queue
import socket
import threading
```

- `socket`: Used for connection attempts.
- `threading`: Runs multiple scanning functions simultaneously.
- `Queue`: Ensures each port is scanned only once by multiple threads.

### Global Variables

```python
target = "127.0.0.1"
queue = Queue()
open_ports = []
```

### Defining Ports to Scan

```python
def get_ports(mode):
    if mode == 1:
        for port in range(1, 1024):
            queue.put(port)
    elif mode == 2:
        for port in range(1, 49152):
            queue.put(port)
    elif mode == 3:
        ports = [20, 21, 22, 23, 25, 53, 80, 110, 443]
        for port in ports:
            queue.put(port)
    elif mode == 4:
        ports = input("Enter your ports (separate by space):").split()
        ports = list(map(int, ports))
        for port in ports:
            queue.put(port)
```

- Mode 1: Scans standardized ports.
- Mode 2: Scans up to 48,128 reserved ports.
- Mode 3: Focuses on crucial ports.
- Mode 4: Allows manual input.

## Multithreading for Speed

### Worker Function

```python
def worker():
    while not queue.empty():
        port = queue.get()
        if portscan(port):
            print("Port {} is open!".format(port))
            open_ports.append(port)
```

This function retrieves port numbers from the queue and scans them. If a port is open, it gets added to `open_ports`.

### Running the Scanner

```python
def run_scanner(threads, mode):
    get_ports(mode)
    thread_list = []
    for _ in range(threads):
        thread = threading.Thread(target=worker)
        thread_list.append(thread)
    for thread in thread_list:
        thread.start()
    for thread in thread_list:
        thread.join()
    print("Open ports are:", open_ports)
```

This function:
1. Loads ports based on the selected mode.
2. Creates and starts the desired number of threads.
3. Waits for all threads to finish before printing the open ports.

### Example Execution

```python
run_scanner(100, 1)
```

This scans all standardized ports using 100 threads, achieving around 100 scans per second. The results might look like:

```
Port 22 is open!
Port 25 is open!
Port 80 is open!
Port 443 is open!
Open ports are: [22, 25, 80, 443]
```

## Conclusion

This tutorial demonstrated how to build a simple yet efficient Python-based port scanner using multithreading. You can customize and expand it further, but always use it ethically and within legal boundaries.

For additional resources:
- Download Full Source Code: [Click Here]
- Download This Tutorial as PDF: [Click Here]
- Follow NeuralNine on Instagram: [Click Here]

