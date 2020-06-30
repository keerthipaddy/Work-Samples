---
layout: defaut
title: Home
---

# Release Notes
Nuix Workstation 8.6 release contains upgrades, enhancements, resolved issues, and some new features. This document provides the highlights of this release.


## New Features
The following new features are available with this release:

### Improvements to MSAB Mobile Evidence Data  
This release is aimed at improving the accuracy of processing and presentation of MSAB data in Workstation. The following improvements are made:


#### Supports XRY XML/ZIP Image for Export Types
A Reports directory is added at the same level as the image type folder to include the file name and file metadata information. This directory is not added if there are no report files found.

#### Supported report file types include: .txt, .ods, .odt, .docx, .gpx, .html, .json, .kmz, .pdf, .xlsx.
Users are able to view the content (via Native viewer) of any supported report files.  


#### Simplified representation of XRY logs 
Users can search relevant documents easily by viewing all XRY logs in a single document instead of one document per log entry. An XRY Log document is added to include all the logs, one line per log entry. The following enhancements have been made:

#### Detect XRY logs as a new MIME type (under MIME types > Logs).
* XRY logs can be searched using the new MIME type.
* Enable Process Text in the Default processing profile.
* Enable Process Text in the Default_Mobile processing profile. 
* Non-English characters in the XRY log file appear with a question mark ?. 

## Licence Updates for Custom Named Entities and Social Media Extraction
Improved licensing for Social Media Extraction and Custom Named Entities, thus extracting more intelligence. 

Note: Extracting data from named entities and social media is now made available to all users with a Case_Creation license feature. Users with a Case_Creation license feature do not need any specific plus feature to use these functionalities. 

### Custom Named Entities 
Custom Named Entities is now available to users with a Case_Creation license using Workstation. Note: Nuix Data Finder (NDF) plugin requires the SENSITIVE_DATA_FINDER plus feature enabled.  

Users can access the Custom Named Entities feature from: 

* Global Options, then Custom Named Entities
* Global Options, then Named Entity Profiles
* Data Processing Settings, then Use custom named entity profile

### Social Media Extraction
Social media can be extracted by users with a Workstation Case_Creation licence feature, where users will be able to process social media data for Facebook, WhatsApp, and Line Chat, without any restrictions.

Note: This licence feature change does not include Twitter. Extracting data from Twitter (network data) requires the NETWORK_DATA license feature with the plus feature enabled.
Refer to Adding Real Time Evidence in the Workstation User Guide for more information. 
The licencing portal is updated with the following licence modification for social media formats, Extraction of social media formats- Facebook, WhatsApp (available by default from v8.6). 


