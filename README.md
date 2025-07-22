# 🌍 Real-Time Disaster Alert System using AWS 🚨

This project simulates a real-time disaster alert system using AWS serverless services. It automatically monitors disasters (real-time and manual via CSV), stores them in a database, and notifies users via email alerts.

---

## 📽️ Demo Video

Watch the working demo of this project on LinkedIn:  
👉 [Demo Video Link](https://www.linkedin.com/posts/devaprasath-r_aws-cloudcomputing-serverless-activity-7353416563107995650-hSpg?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEHEaGMBhXAZOXoahggCFiAnnYXJ81VotV8)

---

## 📌 Project Description

This cloud-native system is designed to simulate a global disaster alerting mechanism for emergency response use cases. It integrates various AWS services in a fully automated, serverless environment to:
- Automatically check for global disasters daily
- Accept manual disaster data uploads
- Send immediate alerts via email
- Store and organize disaster records in a centralized database

---

## ⚙️ How It Works

### 1. **Real-Time Monitoring**
- **Amazon EventBridge** triggers a scheduled event every day.
- This invokes an **AWS Lambda** function that checks if any disasters have occurred (using dummy logic for simulation).
- If a disaster is found, details are stored in **Amazon DynamoDB** and an email is sent via **Amazon SNS**.

### 2. **CSV Upload for Manual Input**
- A user uploads a CSV file with disaster data to **Amazon S3**.
- This triggers a separate **Lambda** function.
- The function parses the CSV and:
  - Saves each record into **DynamoDB**
  - Sends an alert email for each entry using **SNS**

---

## 🛠️ Tech Stack / AWS Services Used

- **AWS Lambda** – Serverless compute to process disasters and CSV files
- **Amazon S3** – For uploading disaster input files
- **Amazon DynamoDB** – NoSQL database to store disaster data
- **Amazon SNS** – To send real-time alert notifications via email
- **Amazon EventBridge** – For scheduling daily disaster checks
- **AWS IAM** – For secure role-based access to AWS resources

---

## Architecture Diagram
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/335ee819-fb1d-4cc0-87f4-9cd754ca7855" />

---
## ✅ Features

- 🕒 **Automated Daily Disaster Check**
- 📥 **CSV Upload Support**
- 📧 **Real-Time Email Alerts**
- ☁️ **100% Serverless Architecture**
- 🗃️ **Persistent Data Storage in DynamoDB**
- 🔒 **Fine-Grained Permissions via IAM**

---

## 🚀 How to Use

1. **Upload a CSV File to S3**
   - Use the provided `disaster_sample.csv` file.
   - Lambda gets triggered, alerts are sent, and data is stored.

2. **Wait for the Scheduled Check**
   - EventBridge triggers the checker Lambda function once per day.
   - If simulated disaster found → alert sent → data saved.

---

## 🧪 Sample CSV Format

```csv
DisasterType,Location,Severity,Description,Time
Flood,Chennai,Severe,Heavy rainfall causing floods,2025-07-22T09:00:00
Earthquake,Delhi,Moderate,Tremors felt across NCR,2025-07-2211:30:00



