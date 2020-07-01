Workstation extracts intelligence from processed data in the form of named entities. Named Entities are objects resembling a specific data pattern. Workstation extracts and indexes these values for analysis. These values are recognized from matches based on pre-defined regular expression pattern searches utilized by Workstation. Named Entities identify specific data sets and are useful for analysis as they enable information such as companies, personal IDs, names, or phone numbers to be brought to the surface of the data set. Named Entity identification and extraction takes place during processing and is extracted from item content (text), properties, or both.

Workstation has an enhanced entity model with additional flexibility and the ability to extract entity information from a set of available default regular expressions. The current default named entities available are Company, Credit Card, Personal ID, Email, Money, Person, Phone Number, Country, IP Address, URL.

# Prerequisites
The Custom Named Entities feature is enabled to users with a Case_Creation license using Workstation from v8.6 onwards. For earlier versions, contact Nuix support at https://nuix.service-now.com/support for license recommendations.

Users can access the Custom Named Entities feature from: 
- Global Options, then Custom Named Entities
- Global Options, then Named Entity Profiles
- Data Processing Settings, then Use custom named entity profile

> Note: The Nuix Data Finder (NDF) plugin requires the SENSITIVE_DATA_FINDER plus feature to be enabled.  

# Enabling Named Entities
The Evidence Processing Settings must be enabled to identify named entities within the data set for further analysis. 

## Data Processing Settings
Conduct processing only over the text content of an item and/or search within the metadata properties associated with an item from the highlighted options shown below. 

Options | Descritpion
-------- | -----------|
Extract named entities from text | This is the traditional entity processing option. It ensures Workstation extracts entities from the text content of supported file types such as documents, emails, and other fully supported mime types. The Include text stripped items option enables you to include text stripped items while extracting named entities from text. For files that Workstation does not support, Workstation text strips the data and presents it to you. If the stripped out text contains entities, enabling this option ensures that they are extracted and presented within the entity reports of Workstation. Text Stripping is a process used when Workstation can identify an item’s filetype but is unable to cleanly extract all text and metadata in accordance with the file type’s API. The result is a searchable data item, but the text may be garbled or not properly formatted. Text Stripping scans the bytes of the data item and looks for runs of string data at least three characters long. 
Extract named entities from properties |	Enables you to search within the metadata properties associated with an item where it identifies entities contained with the metadata and properties of a supported file type. For supported log files or databases where the fields (which are directly mapped to metadata properties in Workstation) contain any entities, these are found and extracted by Workstation. 
Use custom named entities profile | Enables you to select the custom named entity profile for processing. Once this option is selected, the drop-down list is enabled for selection that lists the named entity profiles to choose from. Ensure the Extract named entities from text option or Extract named entities from properties is selected for the Use custom named entities profile drop-down option to be enabled.

The entity settings can be used in any combination depending on the use case. If you are working with unsupported file types, which are malware scripts and code, selecting Include text stripped items helps in extracting entities from the ASCII text, which is stripped from the given files.

In contrast, when dealing with log files like IIS, Apache, or Windows event logs, you must select Extract named entities from properties to ensure any entity values contained with the log file fields are identified and presented within Workstation. 

> Note: Once processed, matched entities are displayed in a separate group for Custom Named Entities. However, if no profile is selected to the Data Processing Settings then only the built-in Named Entity will be processed. Changes done to the profile will be reflected once the evidence is reloaded.

Named Entity Profiles can be added directly as a Data Processing Setting from the Advanced option while adding case evidence.

# Mime Type Settings
The Mime Type Settings tab lists the file types and file categories that Workstation processes. Mime type settings allow selecting the file types that users would like named entities extracted across. Further flexibility of the named entity framework allows users to specify not only where entities should be identified, but also the file types from which they should be extracted. This is controlled by selecting the Entities column on the MIME Type Settings tab of the Evidence Processing Settings to select or deselect categories or even specific types of files for which users would like named entity recognition to be processed.

This feature allows a user, as an investigator, to specifically target individual (or groups of) files, with the chosen entity options, ensuring to get to the key data even faster.

> Tip: If your primary interest is in the IP addresses that contain system files or unsupported files, you can deselect every other MIME type and further improve your investigation speeds. In the event you decide you need to extract entities from more file types, you can do so by reloading items from source data and changing the MIME type settings accordingly.
