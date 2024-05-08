# PII Tools

## Download
Latest version: https://github.com/splunk/pii-tools/releases/download/v0.0.1/pii_tools-0.0.1.tar.gz

## Background
This Splunk App provides tools to detect and handle PII.

This app was created by Matthew Moore, and with the help of the FDSE team has been made Splunk Cloud compatible.

There's a write-up about this app based on the .conf talk here: https://lantern.splunk.com/Splunk_Platform/Use_Cases/Use_Cases_Security/Compliance/Defining_and_detecting_Personally_Identifiable_Information_(PII)_in_log_data

Also available is a recording from .conf 2022 which presents the app: https://conf.splunk.com/files/2022/recordings/SEC1418C_1080.mp4

## Setup
[Download](#download) and install the pii-tools Splunk app.

### Install Dependencies
Some of the machine learning functionality requires these apps to be installed:
- Python for Scientific Computing: https://splunkbase.splunk.com/apps?page=1&keyword=python+for+scientific+computing&filters=product%3Asplunk%2Fsupport%3Asplunk
  - Choose the version specific to your platform. For example https://splunkbase.splunk.com/app/2882 for Linux.   
- Splunk Machine Learning Toolkit: https://splunkbase.splunk.com/app/2890

### Configuration
For the Splunk Machine Learning Toolkit, set the permission for macro `confusionmatrix(2)` to Global:
1. In Splunk click Settings > Advanced Search
2. Click 'Search macros'
3. Set the app filter to 'Splunk Machine Learning Toolkit'
4. Search for 'confusionmatrix'
5. Configure 'Permissions' under the Sharing column
6. Set to 'All apps' which changes the sharing to 'Global'

<img width="1402" alt="image" src="https://github.com/splunk/pii-tools/assets/129806322/37e4e29d-be8e-485a-9995-a63d6d0de810">
<img width="1274" alt="image" src="https://github.com/splunk/pii-tools/assets/129806322/459b2055-e2d1-44a8-96b5-13aff2a90fcb">


## About Dashboards
### PII Analytics
- The input field 'ML Model Name' is user-provided. The SPL will generate a ML model with this name, which is stored as a lookup table file.

## Further Reading
- Splunk Machine Learning Toolkit User Guide: https://docs.splunk.com/Documentation/MLApp/latest/User/WelcometoMLTK


<details>
  <summary>Archived</summary>
  
  ## Package

Use SLIM instead...
https://dev.splunk.com/enterprise/reference/packagingtoolkit/packagingtoolkitcli/#slim-package

https://dev.splunk.com/enterprise/docs/releaseapps/packageapps/
```
# Make sure to remove all local files first!
# E.g. metadata/local.meta
./splunk package app pii-tools
```

## App Vetting
https://dev.splunk.com/enterprise/docs/releaseapps/cloudvetting

## Code Snippets
### Symbolic Link - Splunk Enterprise
```
ln -s path/to/pii-tools/app /Applications/Splunk/etc/apps/pii-tools
```
### Remove `local.meta` files
```
find . -name 'local.meta' | xargs rm
```
</details>
