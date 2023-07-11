# PII Tools
## What is this
Splunk App which provides tools to detect and handle PII.

## Background
This app was created by Matthew Moore.
FDSE team has been involved with helping make this app production-ready.
We aim to publish this on Splunkbase (eventually).
Note: This documentation is a WIP.

## Dependencies
Some of the machine learning functionality requires these apps:
- Python for Scientific Computing (whichever variant suits your OS)
- Splunk Machine Learning Toolkit

## Setup
- Install this app: get the latest build by going to Actions > Build and Release > Click latest main workflow > Artifacts
- MLTK: the `confusionmatrix(2)` macro sharing needs to be set to Global.
## About Dashboards
### PII Analytics
- The input field 'ML Model Name' is user-provided. The SPL will generate a ML model with this name, which is stored as a lookup table file.
## Package
Use SLIM instead...
https://dev.splunk.com/enterprise/reference/packagingtoolkit/packagingtoolkitcli/#slim-package
---
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
