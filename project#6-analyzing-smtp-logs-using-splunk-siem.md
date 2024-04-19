# Analyzing SMTP Log Files Using Splunk SIEM

## Introduction
SMTP (Simple Mail Transfer Protocol) log files contain valuable information about email communication, including sender and recipient addresses, timestamps, email subjects, and more. Analyzing SMTP logs using Splunk SIEM enables security professionals to monitor email traffic, detect anomalies, and identify potential security threats.

## Project Overview
In this project, we will upload sample SMTP log files to Splunk SIEM and perform various analyses to gain insights into email communication within the network.

## Prerequisites
Before starting the project, ensure the following:
- Splunk instance is installed and configured.
- SMTP log data sources are configured to forward logs to Splunk.

## Steps to Upload Sample SMTP Log Files to Splunk SIEM

### 1. Prepare Sample SMTP Log Files
- Obtain sample SMTP log files in a suitable format (e.g., text files).
- Ensure the log files contain relevant SMTP events, including timestamps, sender and recipient addresses, email subjects, etc.
- Save the sample log files in a directory accessible by the Splunk instance.

### 2. Upload Log Files to Splunk
- Log in to the Splunk web interface.
- Navigate to **Settings** > **Add Data**.
- Select **Upload** as the data input method.

### 3. Choose File
- Click on **Select File** and choose the sample SMTP log file you prepared earlier.

### 4. Set Source Type
- In the **Set Source Type** section, specify the source type for the uploaded log file.
- Choose the appropriate source type for SMTP logs (e.g., `mail` or a custom source type if applicable).

### 5. Review Settings
- Review other settings such as index, host, and sourcetype.
- Ensure the settings are configured correctly to match the sample SMTP log file.

### 6. Click Upload
- Once all settings are configured, click on the **Review** button.
- Review the settings one final time to ensure accuracy.
- Click **Submit** to upload the sample SMTP log file to Splunk.

### 7. Verify Upload
- After uploading, navigate to the search bar in the Splunk interface.
- Run a search query to verify that the uploaded SMTP events are visible.

Steps to Analyze SMTP Log Files in Splunk SIEM

