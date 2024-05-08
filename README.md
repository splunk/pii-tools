# PII Tools

## Download
Latest version: https://github.com/splunk/pii-tools/releases/download/v0.0.1/pii_tools-0.0.1.tar.gz

## Background
This Splunk App provides tools to detect and handle PII.

This app was created by Matthew Moore, and with the help of the FDSE team has been made Splunk Cloud compatible.

There's a write-up about this app based on the .conf talk here: https://lantern.splunk.com/Splunk_Platform/Use_Cases/Use_Cases_Security/Compliance/Defining_and_detecting_Personally_Identifiable_Information_(PII)_in_log_data

And a talk by Matthew from .conf 2022 explain the app: https://conf.splunk.com/files/2022/recordings/SEC1418C_1080.mp4

## Setup
[Download](#download) and install the pii-tools Splunk app.

### Install Dependencies
Some of the machine learning functionality requires these apps to be installed:
- Python for Scientific Computing: https://splunkbase.splunk.com/apps?page=1&keyword=python+for+scientific+computing&filters=product%3Asplunk%2Fsupport%3Asplunk
- Splunk Machine Learning Toolkit: https://splunkbase.splunk.com/app/2890

### Configuration
For the Splunk Machine Learning Toolkit, set the permission for macro `confusionmatrix(2)` to Global.


## About Dashboards
### PII Analytics
- The input field 'ML Model Name' is user-provided. The SPL will generate a ML model with this name, which is stored as a lookup table file.
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
