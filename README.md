# ETL Pipeline with Microsoft SSIS

This project demonstrates how to create an ETL (Extract, Transform, Load) pipeline using Microsoft SQL Server Integration Services (SSIS). The pipeline addresses four different data integration problems using SSIS.

## Table of Contents

1. [Introduction](#introduction)
2. [Problem 1: Consuming a REST API](#problem-1-consuming-a-rest-api)
    - [Problem Statement](#problem-statement)
    - [Solution](#solution)
    - [Step-by-Step Implementation](#step-by-step-implementation)
        - [Create the Database Table](#create-the-database-table)
        - [Set Up SSIS Package](#set-up-ssis-package)
        - [Configure the Script Task](#configure-the-script-task)
        - [C# Code Explanation](#c-code-explanation)
        - [Screenshots](#screenshots)
            - [SSIS Package Overview](#ssis-package-overview)
            - [Script Task Editor](#script-task-editor)
            - [C# Script](#c-script)
            - [SQL Server Table](#sql-server-table)
        - [How to Run](#how-to-run)
    - [Prerequisites](#prerequisites)
3. [Problem 2: Title of Problem 2](#problem-2-title-of-problem-2)
4. [Problem 3: Title of Problem 3](#problem-3-title-of-problem-3)
5. [Problem 4: Title of Problem 4](#problem-4-title-of-problem-4)
6. [Conclusion](#conclusion)

## Introduction

This project demonstrates various ETL tasks using Microsoft SSIS. Each problem focuses on a different aspect of data integration, utilizing SSIS to solve these tasks efficiently.

## Problem 1: Consuming a REST API

### Problem Statement

Consume any REST API and load the response to the database. You don’t have to load all the response fields; 3 or 4 is sufficient. For this example, we use a REST API that searches for universities. We create a database table named `University` with three columns: `name`, `country`, and `alpha_two_code`, and load those fields only.

### Solution

To solve this problem, we use a Script Task in SSIS and write a C# script to consume the REST API, extract the necessary fields, and load the data into the SQL Server database.

### Step-by-Step Implementation

#### Create the Database Table

Create a table named `University` in your SQL Server database with the following columns:

```sql
CREATE TABLE University (
    Name NVARCHAR(255),
    Country NVARCHAR(255),
    AlphaTwoCode NVARCHAR(10)
);
