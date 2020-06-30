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

## Enhancements
The following enhancements are available with this release:

- Metadata Profile Groups: The Metadata Profile currently stores metadata identifiers and column width. This improvement separates the user modifications from Metadata Profiles into Metadata Profile Stores and saves them to their own scope. This way the user can control the scope in which the metadata profile should be saved (in a user, local or case) level store. Metadata Profile Builder should be used to change the profiles. 
- User modified Metadata Profiles are stored in the Results View Metadata Profile Store. The store manages to load a Metadata Profile based on if there is a user-modified version of it. The new store keeps profiles in the user scope. 
- Improvements in Promote to Nuix Discover Feature: When audited items are selected to promote to Nuix Discover, their families will also be included. That is, the total item count = Audited items + Audited families of audited items.  This count is reflected in the Summary screen before promoting items to Nuix Discover. The Summary screen includes details such as the case name, selected number of items, and the number of items eligible for promotion from the selected items.
- Metadata profiles are now independent of any updates made to the Workstation results table. This enhancement is made to ensure the user's preferences are stored locally. To update or build a Metadata Profile, access the Metadata Profiles option in Global Options.
- Sensitive data is removed from the logs to improve security when log files are analyzed.

## For Your Information
- The Third-party Connections option in Global Options is now renamed to Configuring Connections.
- The Online Help link is removed from Welcome Screen. To access Online Help from Workstation, go to Help menu and select Online Help.
Upgrades

## Upgrades
For upgrades, note the following:

- ABBYY OCR add-on: ABBYY OCR is upgraded to v12 for Windows and Linux. See Known Issues section for Abbyy v12 support for macOS (this is planned for a future release).
Notable Documentation Updates

## Notable Documentation Updates
The following documentation updates are available with this release:

- Deep Learning Image Classification Feature Guide: The Deep Learning Image Classification feature enables you to configure and label images to your required data structure. This guide assists you with the workflow, including the required configuration and training the model in Workstation.
- Named Entities Extraction Feature Guide: The Named Entities Extraction feature identifies specific data sets and is useful for analysis as it enables information such as companies, personal IDs, names, or phone numbers to be brought to the surface of the data set. This guide assists you with the workflow for Named Entities Extraction, processing settings, creating Custom Named Entities, and Named Entity Profiles.

## Resolved Issues
This release includes resolutions for the following previously known issues:   

### Analysis
Fixed an issue when adding items to a review job on the migrated case from 7.4 to 8.x.
Fixed a potential null-pointer exception in the thumbnails view.
Fixed a potential index out-of-bounds exception in the results view.
Updated documentation for Slack MIME types to reflect JSON support.
Strengthened Global Options -> Configuring Connections -> Remote Collections -> Test connection. Values for the Host field must now be prefixed by http:// or https://.
Fixed an issue with entity counts in the Preview pane.
Added Delivered-To the field as inferred Bcc recipients when parsing emails.
Better error handling of invalid Cloud License Server credentials.
Addressed some OutOfMemoryErrors that could occur when exporting large amounts of data.
Fixed an issue in Filtered Items/Cluster Runs that was affecting the display of some augmented clusters.
Fixed an issue that was potentially causing inaccurate pivot resemblance values when adding items to existing clusters.
Fixed an issue with PDF generation of Microsoft PowerPoint documents that could cause indefinite render times.
Fixed a problem with the Save Search pane that was causing incorrect characters to appear when using Korean input.
Fixed an Elasticsearch issue that was preventing highlighting for some queries.
Improved UI responsiveness when performing searches on large cases.
Added scrollbar to Saved Searches list to allow more items to be selected.
Fixed an issue causing higher than usual CPU usage in Workstation when idle.
Items from load files no longer inherit the item date of the load file.
Corrected the behavior of the scripts menu available when right-clicking in the results pane.
Improved memory usage for case subset export.
Fixed a sorting issue affecting the display of decoded text in the Database Viewer.
Highlights associated with single asterisk wildcard queries are no longer computed for the Preview pane.
Fixed an issue with applying tags to the results of a fuzzy query in Elasticsearch cases.
Fixed an exception that gets thrown if source-data cannot be found when showing preview pane panels.
Improved the performance of the clustering algorithm's cache builder for communication properties.
Fixed an issue with fuzzy hash scoring affecting a limited number of hashes.
Fixed an issue where it was possible to select an unsupported configuration when adding Custom Metadata.

### Extraction
Fixed an unexpected error while processing Slack data in Elasticsearch cases.
Used channel name for grouping messages.
Removed SOCIAL_MEDIA licence restriction for processing Facebook dumps, WhatsApp stores, and LineChat.
Improved validation of bad data when parsing Windows Registry files.
Added support for detecting Debian installer package files (.deb).
Added UI to specify the charset of Zip files. Equivalent to setting nuix.data.zipFileCharsetOverride
Fixed stack overflow when reading invalid Windows Executable files.
Fixed an issue that was causing excessive logging when decrypting some email items.
Fixed an issue where password-protected OneNote sections were not marked as encrypted.
Improved memory usage when processing AccessData FTK Image files.
Fixed an issue for Exchange mailboxes where "From" information may be incorrect for some Outlook items.
Ensure the worker watchdog timeout does not occur during a long-running Lucene or Elasticsearch commit operation.
Improved ZIP extraction to avoid creating an additional temp file in some situations.
Fixed an issue with splitting RAR files when using a password list resulting in the item being marked as corrupt.
Fixed a regression causing image classification to fail.
Fixed an issue where extremely long property names would cause errors in the logs.
Fixed an issue related to the folder structure of the MSAB XRY ZIP file and valid MSAB file.
Fixed an issue related to attachment without binary file.
Allow specifying Custom Named Entity regular expressions using .regexp file format.
Emails without an HTML or RTF body will now always mark their attachments as material items.
Fixed an issue with the Realtime watch folder where large files could be processed before they are fully written to disk. Use -Dnuix.realtime.file.stabilize.wait.time (default 60,000 in milliseconds) to control how long since the last file update before processing.
Implemented extraction of deleted items from the recycle bin from SharePoint (2013 and later).
Added support for handling EML-based Symantec Enterprise Vault DVS files.
X-Ms-Exchange-Processed-By-Bccfoldering is no longer considered an alternative for Bcc.
Added support for MSAB XRY report files to be displayed in the Reports folder and viewable using Native Viewer.
Updated the Cellebrite health activity records to also contain metadata such as distance and step count.
Improved processing of XRY data to remove Unhandled child: tags warnings.
Fixed an issue where XRY calls marked as busy or no answer were not decoded correctly.
Added a switch -Dnuix.data.exchangews.skipLegacyIdShortening=true to skip legacy EWS ID shortening, which triggers slow large folder scan and resulted in EWS connection timeout.
Added support for extracting RAR5 archives.
The Amazon S3 "Last-Modified" property now maps to the standard Nuix property "File Modified".
Blocked external resources in PowerPoint and Word documents from being downloaded during extraction and Imaging.
Fixed an issue where NTFS volume shadow copies extraction was recursing into System Volume Information.
Fixed an issue where the XRY image evidence item naming was not meaningful.
Fixed an issue where if an error occurred while processing large zip files, the item would incorrectly be named 'Error'.
Fixed an issue where File Safe (mfs01) files could not be processed when stored in an Amazon S3 bucket.
Fixed an issue where lengthy numerical values in CSV files were losing precision.
Fixed an issue where the "Decryption Password" field of metadata profile shows no value even if the password exists.

### Export
Fixed a rare issue that was causing incomplete PDF rendering of some Outlook items.
Fixed an issue where UI freezes when trying to OCR a file from a large corrupted zip file.
Fixed a potential deadlock when subsetting items from a compound Lucene/Derby case to an Elasticsearch case.
The number of failed items (if any) is now reported in the case subset export progress dialog.
Support continuous numbering without a delimiter to be used with production set numbering.
Ensure Elastic cases created as a case subset from a Lucene/Derby case will be functioning as expected when doing case subsets back to new Lucene/Derby cases.
Using the switch -Dnuix.storage.storedData.enableAdditionalEmbeddedItems=false can speed up large case subset and export operations.
Do not use this switch if the case has "dynamic child items" created using the "Create New Child Item" feature in the Binary tab within the item Preview pane.
Fixed an issue where text view and PDF view were producing different text.
Updated the failed item count in the OCR summary file to include failed item duplicates.
Production profiles now allow the use of standard or advanced numbering for any export load file type.
Legal export now pauses in response to low disk space events.

### Scripting
Added usingText to Item.Text. It can be used in place of the getReader method, which can throw UnsupportedOperationException.
Fixed Processor#process() so that the profile optionally nominated in Processor#setProcessingProfile(String) is honored.
Fixed a few potential null-pointer exceptions in CredentialsStore.
Fixed an issue with Custodian#setName() that was causing illegal state exceptions.
Fixed an issue causing a null-pointer exception in ProductionSet#setProductionProfileObject().
Fixed an issue where some flags were not updated after a call to `Item#modify` in the case where the text was not also updated.
Fixed an issue where abnormally terminated workers did not restart when the "enableCustomProcessing" option was used with Processor#setProcessingSettings().
Fixed CompoundCase#addChildCase(Case) so that a DuplicateCaseException is always thrown when adding a duplicate case to a compound case.
Updated documentation for DatabaseParameters and DatabaseParametersBuilder.
Added Item#getPhotoDNARobustHash() to retrieve an item's PhotoDNA robust hash value, if it has been computed.
Fixed an issue causing Item#getHighlights(String, Set) to return incorrect offsets when using Windows CRLF line endings.
Fixed an issue where Python in scripted metadata fields is much slower than Ruby/ECMAScript.
Fixed an issue where NullPointerException could be thrown from ExportProcessingJob.getTotalItemCount() or ExportProcessingJob.getFailedItemCount() early in the export process.
Imager
Fixed an issue where Imager memory settings were not applied on Windows.

### Miscellaneous
- Due to issues with new MIME-types, cases created with older versions will need migrating. Migration of Elastic cases requires starting with the switch -Dnuix.elasticsearch.migration.enabled=true.
- Added error handling in PDF tab view.
- Improved performance of the File -> Import -> Import Annotations action.
- Improved performance of migrating 7.7 cases with geolocation data.
- Fixed an issue causing excessive logging when cleaning up temp folders.
- Improved Elasticsearch disk resource usage for annotation operations such as tagging. This requires the updated Nuix Elasticsearch plugin to be installed.
- Disabled changes to Metadata Profiles made from the Results View by default. Any column ordering or resizing done within the Results View will not be written back to the Metadata Profile.
- Set -Dnuix.resultsView.saveToMetadataProfile=true to allow changes made in the Results View to be written back to the Metadata Profile.
- Suppress exception dialogs when retrieving items in the Thumbnail view. The exception details can still be seen in the logs.
- Licences with CASE_CREATION can now make use of "Custom Named Entities" in Workstation.
- Added support for Metadata profile grouping.
- Relaxed the worker temp directory maximum path length from 76 to 200 due to improvements within the Lotus Notes libraries.
- Added retry logic when accessing Derby database files to account for unreliable network file systems.
- Login credentials are cached when connecting through NMS in relay mode.
- Updated Search Fields documentation to include syntax for PhotoDNA queries.
- Fixed an issue "file system provider is missing" when using a loadfile.
- Forcing application exit after 15s if a graceful shutdown is not possible. A timeout can be set with the switch nuix.application.forceShutdownTimeout (ms).

### Unexpected Errors 
- Unhandled exception in Workbench: When performing a long-running OCR, at the end of the logs there is an exception that triggered an error dialog to appear. 

### Translation
- Switch for Spanish language translation is changed due to an ABBYY issue. Users need to use the following switch:

`-Duser.language=es -Duser.country=MX`
Note: The -Duser.language=es -Duser.country=419 is no longer supported and is replaced with the above switch. 

## Known Issues
The following known issues are found in this release.  

- ABBYY upgrade for macOS: Users can still download the Workstation macOS bundle for v8.6 to get the current supported OCR version. 
