\# Cloud Data Deduplication System



\## Overview

This project is a cloud-based system that detects and prevents duplicate data storage using hashing techniques.



\## Features

\- Identifies redundant data using SHA-256 hashing

\- Validates new data against existing records

\- Prevents duplicate entries

\- Stores unique data in AWS S3

\- Stores metadata in DynamoDB



\## Technologies Used

\- Python

\- AWS S3

\- AWS DynamoDB

\- Boto3



\## How It Works

1\. User inputs data

2\. System generates hash

3\. Hash is checked in DynamoDB

4\. If duplicate → rejected

5\. If unique → stored in S3 and DynamoDB



## Setup Instructions:

### 1. Clone the repository

git clone https://github.com/YOUR_USERNAME/cloud-dedup-system.git

cd cloud-dedup-system


### 2. Create virtual environment

python -m venv venv
.\venv\Scripts\activate


### 3. Install dependencies

pip install -r requirements.txt


### 4. Configure AWS
Make sure you have AWS CLI installed, then run:

aws configure


Enter:
- Access Key ID
- Secret Access Key
- Region (e.g., ap-south-1)
- Output format: json

### 5. Create AWS Resources
- Create an S3 bucket
- Create a DynamoDB table:
  - Table name: `dedup-table2`
  - Partition key: `hash` (String)

### 6. Update configuration
In `utils.py`, update:

BUCKET_NAME = 'your-bucket-name'


### 7. Run the application

python app.py

