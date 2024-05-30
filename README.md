# SIEM-Project
Azure-Sentinel-Configuration

Description: 
  - This project demonstrates how to configure Azure Sentinel (Microsoft's cloud SIEM) to ingest and analyze custom logs containing geographic information from RDP brute force attacks. 
The setup includes using custom PowerShell scripts to extract metadata, configuring Log Analytics Workspace, and displaying attack data on a world map in Azure Sentinel.

Prerequisites:
  - Azure account with access to Azure Sentinel
  - Windows Event Viewer logs
  - PowerShell installed on your system

Setup:

Clone the Repository:
  - Clone this repository to your local machine
  - git clone https://github.com/kimurakits/Azure-Sentinel-Configuration.git
  - cd Azure-Sentinel-Configuration

Run PowerShell Script:
  - Use the provided PowerShell script to extract metadata from Windows Event Viewer and forward it to a third-party API to derive geolocation data:
  - .\extract_metadata.ps1


Configure Log Analytics Workspace:
  - Navigate to your Log Analytics Workspace in the Azure portal.
  - Go to the "Custom Logs" section under "Settings".
  - Add a new custom log and configure the log format to match your data.
  - Ingest the custom logs containing geographic information (latitude, longitude, state/province, and country).


Configure Custom Fields:
  - In the Log Analytics Workspace, go to "Settings" -> "Custom Fields".
  - Add custom fields to parse the geographic data from your logs:
  - Latitude
  - Longitude
  - State/Province
  - Country


Create Azure Sentinel Workbook:

Use the KQL queries provided in the repository to create a workbook in Azure Sentinel to display global attack data:
  - Navigate to Azure Sentinel in the Azure portal.
  - Go to "Workbooks" and create a new workbook.
  - Use the KQL queries from KQLQueries.md to configure the workbook to display RDP brute force attack data on a world map.


Usage:

Once the setup is complete, Azure Sentinel will display RDP brute force attack data on a world map according to physical location and magnitude of attacks. 
You can monitor and analyze these attacks to enhance your security posture.


Scripts and Queries
  - extract_metadata.ps1: PowerShell script to extract metadata from Windows Event Viewer.
  - KQLQueries.md: Kusto Query Language (KQL) queries for configuring Azure Sentinel workbook.


Screenshots
Include screenshots to visually represent the setup process and final output:

PowerShell Script Execution

Log Analytics Workspace Configuration

Azure Sentinel Workbook


