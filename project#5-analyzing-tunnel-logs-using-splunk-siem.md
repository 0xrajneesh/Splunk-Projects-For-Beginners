# Analyzing Tunnel Log Traffic Using Splunk SIEM

## Introduction
Tunnel log traffic from Zeek IDS (formerly known as Bro IDS) contains information about various tunneling protocols such as GRE, IPv4, IPv6, etc. Analyzing tunnel log traffic using Splunk SIEM enables security professionals to monitor tunneling activities, detect anomalies, and identify potential security threats.

## Project Overview
In this project, we will upload sample tunnel log traffic from Zeek IDS to Splunk SIEM and perform various analyses to gain insights into tunneling activities within the network.

## Prerequisites
Before starting the project, ensure the following:
- Splunk instance is installed and configured.
- Tunnel log data sources from Zeek IDS are configured to forward logs to Splunk.

## Steps to Upload Sample Tunnel Log Traffic from Zeek IDS to Splunk SIEM

### 1. Prepare Sample Tunnel Log Files
- Obtain sample [tunnel log files](https://www.secrepo.com/maccdc2012/tunnel.log.gz) from Zeek IDS in a suitable format (e.g., text files).
- Ensure the log files contain relevant tunneling events, including timestamps, source and destination IP addresses, tunneling protocols, etc.
- Save the sample log files in a directory accessible by the Splunk instance.

### 2. Upload Log Files to Splunk
- Log in to the Splunk web interface.
- Navigate to **Settings** > **Add Data**.
- Select **Upload** as the data input method.

### 3. Choose File
- Click on **Select File** and choose the sample tunnel log file you prepared earlier.

### 4. Set Source Type
- In the **Set Source Type** section, specify the source type for the uploaded log file.
- Choose the appropriate source type for Zeek IDS tunnel logs (e.g., `bro` or a custom source type if applicable).

### 5. Review Settings
- Review other settings such as index, host, and sourcetype.
- Ensure the settings are configured correctly to match the sample tunnel log file.

### 6. Click Upload
- Once all settings are configured, click on the **Review** button.
- Review the settings one final time to ensure accuracy.
- Click **Submit** to upload the sample tunnel log file to Splunk.

### 7. Verify Upload
- After uploading, navigate to the search bar in the Splunk interface.
- Run a search query to verify that the uploaded tunnel events from Zeek IDS are visible.
  


## Steps to Analyze Tunnel Log Traffic in Splunk SIEM


### 1. Search for Tunnel Events
- Open Splunk interface and navigate to the search bar.
- Enter the following search query to retrieve tunnel events from Zeek IDS:
```
index=<your_tunnel_index> sourcetype=<your_tunnel_sourcetype>
```

### 2. Extract Relevant Fields
- Identify key fields in tunnel logs such as timestamps, source and destination IP addresses, tunneling protocols, etc.
- Use Splunk's field extraction capabilities or regular expressions to extract these fields for better analysis.
- Example extraction command:
```
| rex field=_raw "<regex_pattern>"

```

### 3. Analyze Tunneling Protocols
- Determine the distribution of SSH commands executed:
```
index=<your_tunnel_index> sourcetype=<your_tunnel_sourcetype> tunnel_protocol=GRE
| stats count by tunnel_protocol
```

### 4. Detect Anomalies
- Look for unusual patterns or anomalies in GRE tunneling activity:
```
index=<your_tunnel_index> sourcetype=<your_tunnel_sourcetype> tunnel_protocol=GRE
| timechart count by _time
```

### 5. Monitor GRE Tunneling Activity
- Monitor GRE tunneling activity over time:
```
index=<your_tunnel_index> sourcetype=<your_tunnel_sourcetype> tunnel_protocol=GRE
| timechart span=1h count by _time

```


## Conclusion
In conclusion, integrating Zeek IDS tunnel logs into Splunk SIEM provides security teams with the necessary visibility and tools to proactively monitor, detect, and respond to tunneling-related security incidents, ultimately enhancing overall cybersecurity posture and resilience against emerging threats.

Feel free to customize these steps according to your specific use case and requirements. 

Happy analyzing!



