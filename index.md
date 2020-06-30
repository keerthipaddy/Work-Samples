---
layout: defaut
title: home
---

Alt-H1
======
Release Notes

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
..*XRY logs can be searched using the new MIME type.
..*Enable Process Text in the Default processing profile.
..*Enable Process Text in the Default_Mobile processing profile. 
..*Non-English characters in the XRY log file appear with a question mark ?. 
