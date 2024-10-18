---
title: DBMS Basics
author: Aditya Tomar
pubDatetime: 2024-10-18T21:22:00Z
slug: dbms-basics
featured: true
draft: false
tags:
    - dbms
    - database
    - basics
ogImage: ""
description: This is the example description of the example post.
---

# DBMS Basics

This document provides a list of basic Database Management System (DBMS) concepts and commands to help you get started with understanding and using databases effectively.

## Introduction to DBMS
- **DBMS**: Software that uses a standard method to store and organize data.
- **RDBMS**: Relational Database Management System, a type of DBMS based on the relational model.

## Key Concepts
- **Database**: An organized collection of data.
- **Table**: A collection of related data entries consisting of rows and columns.
- **Schema**: The structure that defines the organization of data in a database.

## SQL Basics
- **SQL**: Structured Query Language, used to communicate with databases.
- `SELECT`: Retrieve data from a database.
- `INSERT`: Add new data to a database.
- `UPDATE`: Modify existing data in a database.
- `DELETE`: Remove data from a database.

## Data Types
- **Integer**: Whole numbers.
- **Varchar**: Variable-length string.
- **Date**: Date values.

## Constraints
- **Primary Key**: Uniquely identifies each record in a table.
- **Foreign Key**: A field in one table that uniquely identifies a row of another table.
- **Unique**: Ensures all values in a column are unique.
- **Not Null**: Ensures a column cannot have a NULL value.

## Normalization
- **Normalization**: Process of organizing data to reduce redundancy.
- **1NF (First Normal Form)**: Ensures each column contains atomic values.
- **2NF (Second Normal Form)**: Ensures all non-key attributes are fully functional dependent on the primary key.
- **3NF (Third Normal Form)**: Ensures no transitive dependency for non-prime attributes.

## Indexing
- **Index**: A database object that improves the speed of data retrieval.
- **Clustered Index**: Sorts and stores the data rows in the table based on their key values.
- **Non-Clustered Index**: Contains a sorted list of references to the table data.

## Transactions
- **Transaction**: A sequence of database operations that are treated as a single unit.
- **ACID Properties**: Ensures reliable processing of database transactions.
  - **Atomicity**: Ensures that all operations within a transaction are completed successfully.
  - **Consistency**: Ensures the database remains in a consistent state before and after the transaction.
  - **Isolation**: Ensures that transactions are securely and independently processed.
  - **Durability**: Ensures that the results of a transaction are permanently stored in the database.

## Backup and Recovery
- **Backup**: Creating a copy of the database to protect against data loss.
- **Recovery**: Restoring the database to a correct state in case of failure.

These concepts and commands should help you get started with basic DBMS understanding and usage.
