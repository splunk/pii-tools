# PII Tools
## What is this
Splunk App which provides tools to detect and handle PII.

## Background
This app was created by Matthew Moore.
FDSE team has been involved with helping make this app production-ready.
We aim to publish this on Splunkbase (eventually).

## Documentation
TODO - need to work with Matthew to produce this

## Package
https://dev.splunk.com/enterprise/docs/releaseapps/packageapps/
```
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