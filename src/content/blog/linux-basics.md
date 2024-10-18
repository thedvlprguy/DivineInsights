---
title: Linux Basics
author: Aditya Tomar
pubDatetime: 2024-10-18T05:17:19Z
slug: linux-basics
featured: true
draft: false
tags:
    - linux
    - basics
    - commands
ogImage: ""
description: This is the example description of the example post.
---

# Linux Basics

This document provides a list of basic Linux commands to help you get started with file and directory management, system information, networking, and more.

## File and Directory Management
- `ls`: List directory contents.
- `cd [directory]`: Change the current directory.
- `pwd`: Print the current working directory.
- `mkdir [directory]`: Create a new directory.
- `rmdir [directory]`: Remove an empty directory.
- `rm [file]`: Remove a file.
- `rm -r [directory]`: Remove a directory and its contents recursively.
- `cp [source] [destination]`: Copy files or directories.
- `mv [source] [destination]`: Move or rename files or directories.

## File Viewing and Editing
- `cat [file]`: Concatenate and display file content.
- `less [file]`: View file content one screen at a time.
- `nano [file]`: Edit files using the nano text editor.
- `vim [file]`: Edit files using the vim text editor.

## System Information
- `uname -a`: Display all system information.
- `top`: Display tasks and system status.
- `df -h`: Display disk space usage.
- `free -h`: Display memory usage.

## File Permissions
- `chmod [permissions] [file]`: Change file permissions.
- `chown [owner]:[group] [file]`: Change file owner and group.

## Networking
- `ping [host]`: Send ICMP ECHO_REQUEST to network hosts.
- `ifconfig`: Configure network interfaces.
- `curl [url]`: Transfer data from or to a server.

## Process Management
- `ps`: Report a snapshot of current processes.
- `kill [PID]`: Terminate a process by its PID.
- `killall [process_name]`: Terminate all processes with the given name.

## Package Management (Debian-based systems)
- `apt-get update`: Update package lists.
- `apt-get upgrade`: Upgrade all packages.
- `apt-get install [package]`: Install a package.
- `apt-get remove [package]`: Remove a package.

## Miscellaneous
- `echo [text]`: Display a line of text.
- `man [command]`: Display the manual for a command.
- `history`: Show command history.
- `clear`: Clear the terminal screen.

These commands should help you get started with basic Linux operations.
