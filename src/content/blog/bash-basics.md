---
title: Bash Scripting Basics
author: Aditya Tomar
pubDatetime: 2024-10-18T21:22:00Z
slug: bash-scripting-basics
featured: true
draft: false
tags:
    - bash
    - scripting
    - basics
ogImage: ""
description: This is the example description of the example post.
---

# Bash Scripting Basics

This document provides a list of basic Bash scripting commands and concepts to help you get started with writing and executing scripts in a Linux environment.

## Script Structure
- `#!/bin/bash`: Shebang to specify the script interpreter.
- `#`: Comment line.

## Variables
- `variable_name=value`: Define a variable.
- `$variable_name`: Access the value of a variable.

## Input and Output
- `echo [text]`: Print text to the terminal.
- `read [variable]`: Read input from the user.

## Conditional Statements
- `if [ condition ]; then ... fi`: Basic if statement.
- `if [ condition ]; then ... else ... fi`: If-else statement.
- `if [ condition ]; then ... elif [ condition ]; then ... else ... fi`: If-elif-else statement.

## Loops
- `for variable in list; do ... done`: For loop.
- `while [ condition ]; do ... done`: While loop.
- `until [ condition ]; do ... done`: Until loop.

## Functions
- `function_name() { ... }`: Define a function.
- `function_name`: Call a function.

## File Operations
- `touch [file]`: Create an empty file.
- `cat [file]`: Display file content.
- `> [file]`: Redirect output to a file (overwrite).
- `>> [file]`: Redirect output to a file (append).

## String Operations
- `${#string}`: Get the length of a string.
- `${string:position:length}`: Extract substring.

## Arrays
- `array_name=(value1 value2 value3)`: Define an array.
- `${array_name[index]}`: Access array element.
- `${#array_name[@]}`: Get the length of an array.

## Exit Status
- `exit [status]`: Exit the script with a status code.
- `$?`: Get the exit status of the last command.

## Error Handling
- `command || { echo "Command failed"; exit 1; }`: Execute a command and handle errors.

## Debugging
- `bash -x script.sh`: Run a script in debug mode.

These commands and concepts should help you get started with basic Bash scripting.

