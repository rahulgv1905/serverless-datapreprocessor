# 🚀 Serverless Data Preprocessing Pipeline on AWS

A **fully serverless**, **event-driven** data preprocessing pipeline designed using **AWS Lambda**, **S3**, **Glue**, and **QuickSight**. This project automates the entire lifecycle from raw data ingestion to data cleaning, transformation, cataloging, and final visualization — without managing any servers.

---

## 🧠 Problem Statement

Manually preprocessing large datasets before analysis is inefficient, error-prone, and not scalable. This project solves that problem by building an **automated data pipeline** triggered by CSV uploads, using AWS services to validate, transform, and prepare data for business intelligence tools like **Amazon QuickSight**.

---

## 🏗️ Architecture Overview

<img width="1017" height="464" alt="image" src="https://github.com/user-attachments/assets/6be60607-f8ea-4c29-8e8f-9073126c3582" />

---

## 🔁 Workflow Steps

| Step | Component | Description |
|------|-----------|-------------|
| 1️⃣ | **CSV Upload** | User uploads a raw `.csv` file to the `csv-raw-data` S3 bucket. |
| 2️⃣ | **AWS Lambda** | Triggered by S3 event. Reads raw file, performs **basic preprocessing** (e.g., missing values, type fixes), and writes cleaned file to `csv-processed-data` bucket. |
| 3️⃣ | **Processed Data Bucket (S3)** | Stores the output from Lambda after initial preprocessing. |
| 4️⃣ | **AWS Glue Crawler** | Automatically scans the processed bucket and updates the **Glue Data Catalog** with schema information. |
| 5️⃣ | **AWS Glue Data Catalog** | Centralized schema repository to track data structure. |
| 6️⃣ | **AWS Glue Job** | Reads from the Glue Catalog, applies **advanced transformation** or **schema mapping**, and writes output to `csv-final-data` bucket. |
| 7️⃣ | **Amazon QuickSight** | Connects to final S3 bucket and **generates dashboards** for visual analytics. |

---

## 🛠️ Tech Stack

| AWS Service         | Role                                      |
|---------------------|-------------------------------------------|
| **Amazon S3**        | Storage for raw, processed, and final data |
| **AWS Lambda**       | Executes preprocessing logic on file upload |
| **AWS Glue Crawler** | Discovers schema from S3 processed files   |
| **AWS Glue Job**     | Performs advanced transformation tasks     |
| **AWS Glue Catalog** | Stores metadata and schema definitions     |
| **Amazon QuickSight**| Visualizes final data using dashboards     |
| **CloudWatch**       | Monitors Lambda logs and job executions    |

---

## ✅ Features

- ⚡ **Serverless Architecture** – No server provisioning or management.
- 📂 **Automated Ingestion** – Triggered by file uploads.
- 🧼 **Modular Preprocessing** – Split across Lambda and Glue for better separation of concerns.
- 📊 **Visualization Ready** – Connects directly to BI tools like QuickSight.
- 🔁 **Reusable Schema** – Via Glue Catalog for consistent data access.
- 🔔 **Notification Ready** – Extendable with SNS/EventBridge for alerts.

---

## 📁 Project Structure

  
