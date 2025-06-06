# 🔍 Querying Data Lake using Azure Synapse Analytics

This project demonstrates how to use **Azure Synapse Analytics** to query and transform data stored in Azure Data Lake Storage (ADLS). It focuses on using **serverless SQL pools** and **data pipelines** to handle typical business data scenarios such as sales consolidation across branches and gender-based data filtering.

---

## 🧪 Lab Description

**Azure Synapse Analytics** is an integrated analytics platform that enables advanced data analytics, data exploration, and integration across various sources. It combines the capabilities of a modern data warehouse with the flexibility of big data analytics and real-time processing.

This lab shows how to deploy Synapse Analytics, use serverless SQL to query CSV files stored in Data Lake, and execute transformation pipelines for real-world business scenarios.

---

## 🎯 Learning Objectives

By completing this lab, you will be able to:

- Deploy and manage an Azure Synapse Analytics workspace.
- Connect to and manage data in Azure Data Lake Storage Gen2.
- Interact with **Synapse Studio** for data analysis and pipeline development.
- Use serverless SQL pools to query data directly from the Data Lake.
- Create SQL Views to virtualize CSV data.
- Build pipelines to merge and transform data from multiple sources.

---

## 👤 Intended Audience

- Azure Data Engineer candidates (DP-203)
- Cloud Architects
- Data Engineers & DBAs
- Analysts looking to visualize and analyze data in Azure

---

## 🧠 Prerequisites

- Basic understanding of Azure Storage and SQL
- Familiarity with AzCopy and Azure Cloud Shell (helpful but not required)

**Recommended Courses:**
- Introduction to Azure Synapse Analytics
- Using Azure Data Lake Storage Gen2

---

## 🧩 Environment Setup

### ✅ Before
- Azure account with appropriate resource permissions
- Azure Data Lake Storage Gen2 created
- Synapse Analytics workspace created

### ✅ After
- Data uploaded and queryable from Synapse Studio
- Pipelines for data merging and filtering implemented
- SQL Views and JSON output available for advanced analytics

---

## 🧪 Lab Scenarios

### 📁 Case 1: Merging Sales Data from Multiple Branches

**Scenario**: A company has three branches in **Hà Nội**, **Hồ Chí Minh**, and **Đà Nẵng**. Sales data is stored locally in CSV format, and the goal is to consolidate it for centralized analysis.

**Steps**:

1. Configure a **Linked Service** from Synapse to connect with a **Windows File System** that contains the branch data.
2. Use a **Copy Data activity** in Azure Data Factory to read all branch CSVs from the `branch/` folder.
3. Specify the destination container in **Azure Blob Storage** to store the merged file.
4. Run the pipeline and verify the **merged CSV** file.

**Result**: A single consolidated CSV file representing sales from all three branches is stored in Azure Blob Storage.

> 📷 Screenshots: See `screenshots/` folder for pipeline configuration and result visuals.

---

### 👥 Case 2: Filtering Data by Gender and JSON Transformation

**Scenario**: At a specific branch, customer data includes gender information. The business wants to analyze male and female segments separately.

**Steps**:

1. Create a **Data Flow** to apply filters based on gender.
2. Output two separate CSV files: one for **male**, one for **female**.
3. Convert the filtered CSVs into **JSON format** by creating new columns `Male` and `Female` as object arrays.
4. Aggregate and deduplicate the data using **aggregate transformation**.
5. Save the final JSON files for further use.

**Result**: Two clean JSON datasets, one for each gender, containing only unique entries.

> 🕓 Execution Time: Each pipeline ran between 2 to 3 minutes.

---

## 🗂 Directory Structure

