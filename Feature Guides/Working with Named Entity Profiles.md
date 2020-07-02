# Named Entity Extraction - Introduction
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

![Data Processing Settings](https://github.com/keerthipaddy/worksamples/blob/master/images/NE_Evidence%20Processing%20Settings.png)

Options              | Description    |
------------------------------ | ---------------------------------------------------------------------|
Extract named entities from text | This is the traditional entity processing option. It ensures Workstation extracts entities from the text content of supported file types such as documents, emails, and other fully supported mime types. The Include text stripped items option enables you to include text stripped items while extracting named entities from text. For files that Workstation does not support, Workstation text strips the data and presents it to you. If the stripped out text contains entities, enabling this option ensures that they are extracted and presented within the entity reports of Workstation. Text Stripping is a process used when Workstation can identify an item’s filetype but is unable to cleanly extract all text and metadata in accordance with the file type’s API. The result is a searchable data item, but the text may be garbled or not properly formatted. Text Stripping scans the bytes of the data item and looks for runs of string data at least three characters long. 
Extract named entities from properties |	Enables you to search within the metadata properties associated with an item where it identifies entities contained with the metadata and properties of a supported file type. For supported log files or databases where the fields (which are directly mapped to metadata properties in Workstation) contain any entities, these are found and extracted by Workstation. 
Use custom named entities profile | Enables you to select the custom named entity profile for processing. Once this option is selected, the drop-down list is enabled for selection that lists the named entity profiles to choose from. Ensure the Extract named entities from text option or Extract named entities from properties is selected for the Use custom named entities profile drop-down option to be enabled.

The entity settings can be used in any combination depending on the use case. If you are working with unsupported file types, which are malware scripts and code, selecting Include text stripped items helps in extracting entities from the ASCII text, which is stripped from the given files.

In contrast, when dealing with log files like IIS, Apache, or Windows event logs, you must select Extract named entities from properties to ensure any entity values contained with the log file fields are identified and presented within Workstation. 

> Note: Once processed, matched entities are displayed in a separate group for Custom Named Entities. However, if no profile is selected to the Data Processing Settings then only the built-in Named Entity will be processed. Changes done to the profile will be reflected once the evidence is reloaded.

Named Entity Profiles can be added directly as a Data Processing Setting from the Advanced option while adding case evidence.

# Mime Type Settings
The Mime Type Settings tab lists the file types and file categories that Workstation processes. Mime type settings allow selecting the file types that users would like named entities extracted across. Further flexibility of the named entity framework allows users to specify not only where entities should be identified, but also the file types from which they should be extracted. This is controlled by selecting the Entities column on the MIME Type Settings tab of the Evidence Processing Settings to select or deselect categories or even specific types of files for which users would like named entity recognition to be processed.

![Mime Type Settings](https://github.com/keerthipaddy/worksamples/blob/master/images/Named%20Entiies_Mime%20Types.png)

This feature allows a user, as an investigator, to specifically target individual (or groups of) files, with the chosen entity options, ensuring to get to the key data even faster.

> Tip: If your primary interest is in the IP addresses that contain system files or unsupported files, you can deselect every other MIME type and further improve your investigation speeds. In the event you decide you need to extract entities from more file types, you can do so by reloading items from source data and changing the MIME type settings accordingly.

# Search and View Named Entities
In the Results pane, you can view the default entities found in Workstation, related to Company, Credit Card, Email, Money, Personal ID, Phone Number, Country, IP Address, and URL in the result set by selecting View by: Entities. Entities are stored here: *C:\Program Files\Nuix\Nuix Application version\user-data\Named Entities*. Additionally, users can add Named Entities to the Named Entities library by adding the regular expressions file and updating the regex.properties file. See Regular Expression Queries for Named Entities for more information.

Extracted Named Entities can be viewed from: 

- **Results By** in the Results panel: Once you select Entities on the View By selection, you can select the type of entities to view using the Entities dropdown list.
- **Entities tab** in the Preview panel: If Workstation has extracted named entities from an item, the Entities tab will be displayed on the item Preview panel. This tab allows you to select the type of named entities to review and to also filter on them.
- **Filtered Items** in the Document Navigator: Workstation allows you to filter by named entities under the Named Entities menu in the Filtered Items panel under the Document Navigator pane. This filter will be populated only if named entities are identified during the ingestion process for the case. On double-clicking the named entity, the items related to your search appear in the Results view. 

## Search Named Entities 
1. Filter for Named Entities using the Named Entities filter in the Document Navigator.
2. Query entities directly from the Search Bar. Change the Results view to Entities, within the appropriate entity category.
3. Double-click the entity to open a new Workbench tab, with just the items related to your search.
Users can edit and add new named entities.

You can view items that contain an entity by changing your results view to Entity and double-clicking on the entity you'd like. 

### Examples:
- A query of a named entity, View By: Entities and select Credit Card as the entity. This identifies all Credit Card numbers in a group of documents.
- A query to view Company XYZ, select View By: Entities and select Company as the entity. Double-clicking on Company XYZ will open a new Workbench tab containing all items referencing Company XYZ in the results pane.
To search within this list, instead of reverting to searching within the entire case, you must add your search item to the query in the search bar (see example below). If you clear the existing search criteria, it clears the results as well.

For example, after double-clicking on the company entity *Company XYZ*, the search bar has the following query: *named-entities:"company;Company XYZ"*. If you want to search for all PDFs within *Company XYZ*, change the query to look like: *named-entities:"company;Company XYZ" AND mime-type: application/pdf*

# Named Entity Wordlists (.lists)
Named Entity wordlists require a UTF-8 encoded word list file with an extension of .list. The wordlists are stored in *C:\Program Files\Nuix\Nuix Application version\user-data\Named Entities\lists*. A hash character indicates a comment and can be used to specify how the search should operate. By default, it is case sensitive and not based on whole words.

Searches are case sensitive and will locate the word anywhere in the file. For example, searching for the word plan will result in hits where the word planning is found, but not if the word Plan is found.  

| Defaults Values that can be altered |  |
|-----------|----------| 
|#caseInsensitive |	The case need not match, capitalization is ignored.|
|#wholeWords | Match only the whole word.|
|#wholeWordsWhiteSpace | Will match whole words with white space (space, tab, new-line) between them, but not with characters (comma, periods, etc.) between them. For example, #wholeWordsWhiteSpace included in a file searching for Nuix eDiscovery will find Nuix eDiscovery, but not Nuix. eDiscovery.

## Viewing Wordlists in Workstation
The wordlists are processed and added in the Words view in the view pane.
![](https://github.com/keerthipaddy/worksamples/blob/master/images/Wordlist.png)

# Regular Expression Queries for Named Entities
A regular expression is used to describe search patterns in named entities that match patterns of text strings, such as particular characters, numbers, or words. Named Entities are stored as regular expressions files in the Named Entities library in C:\Program Files\Nuix\Nuix Application version\user-data\Named Entities. Users can add Named Entities to the Named Entities library by adding the regular expressions file (regexp) and updating the regex.properties file. 

1. Adding a Named Entity requires a regexp (or .list) file and an icon (.png). The regexp file is a plain text file that will hold your regular expression and an icon that is a .png file, ideally 48 x 48 pixels, or smaller.
2. Copy the regexp or list file into the default directory located here: C:\Program Files\Nuix\Nuix Application version\user-data\Named Entities. Further information needs to be entered into the regexp file to display the new entity. Workstation should be closed and a backup of the file should be made prior to editing it.
3. When editing your regexp file, ensure the first line starts with a # (to indicate a comment) followed by a description of the group the entity is part of, such as a location or named entities, which are the default groups in Workstation. The next line should give the name of the entity, and the last line should provide the name of the filename of the icon to which you want the directory to point. 
For example: If you create a Social Media entity, it should look similar to the example below:
```
NamedEntities.social.group=Custom
NamedEntities.social.title=Social Media
The entity PNG file name must be identical to the way it is written in the regex files.
```
4. Update the regex.properties file with the group and title information.
5. Launch Workstation and select all items, right-click, and select Reload Items from Source data. In the Data Processing Settings, ensure Extract named entities from text and Extract named entitles from properties are enabled.
6. Post-processing, in the Results pane, change the Results view to Entities. Select the Entities dropdown to view the new entity that was added. Select the new entity to see the items identified from reprocessing and added to the entity.

## Performing a Regular Expression Search
To perform a regular expression search, add the forward-slash character (/) to the start and end of the regular expression to be used in the search. For those familiar with regular expressions, the pattern is matched against each word, so using expressions such as the caret (^) to find the start of a line in the text is not possible. Matching is not case sensitive and literal characters must be entered in lowercase.

You can also form complex phrase queries by using spaces within the regular expressions, and “slop” for phrases within regular expressions is supported. A "slop" of a phrase query is to search for words within a certain distance of each other, using the tilde (~) symbol at the end of a phrase query along with a numerical value that indicates the number of unrelated words that can occur in between. 

Some available patterns:
| Syntax | Results | 
| ------ | --------| 
| \d | A digit (0-9)|
| \D | A non-digit |
| [] | One of the characters within the brackets | 
|. | Any character | 
| .* | The same as a multiple character wildcard search |
| \b | A word boundary. Hyphenated words are broken up by word boundaries. This matches hyphen boundaries and the end of a word. |
| ^ | The start of a word. Will not match hyphen boundaries. |
| $ | The end of a word. Will not match hyphen boundaries. |

## Examples

| Query Syntax | Description | 
|---------------|-------------|
| `/apple|orange/` | Matches all items that contain either apple or orange. |
| `/eat|ate apple|orange/ ~2` | Matches all items that contain either eat or ate and then apple or orange, with up to two unrelated terms separating them. Note that only whole words are matched. To match partial words, use wildcard characters. |
| `/gr[eao]y/` | Matches all items that contain either grey, gray, or groy. |
| `/gr[^eao]y/` | Matches all items that contain at least one word starting with gr followed by a character that is not e, a or o, followed by y. This query would match griy and gr3y. |
| `/.oe.* not/` | An example of a phrase query. Matches all items that have a word starting with any letter followed by oe, optionally followed by any other characters then the word not. This query would match "does not", "joe not" and "ioexception not".
| `/0\d{1,3}/` | Matches all items that start with 0 followed by 1 to 3 digits. This query would match 02, 0404, 00 and 080. |
| `/0\d{1,3} \d{3,4} \d{3,4}/ OR /0\d{1,3} \d{6,8}/` | Matches all items that may contain local phone number patterns. The first part of this query would match 02 2328 1929, 043 232 192 and 0404 0233 2333. The second part would match 02 23281929, 043 23221923 and 0404 023323. There are different conventions for how phone numbers are grouped, so you will probably need to adjust this query for different cases. |
| `/[\u0400-\u052f]*/` | Matches all Unicode Cyrillic and Cyrillic Supplement alphabet families. Note that adding the asterisk (*) will highlight whole words for some languages such as Russian and Serbian. |
| `/[\p{InCyrillic}\p{InCyrillic_Supplementary}]*/` | Matches all Unicode Cyrillic and Cyrillic Supplement alphabet families using the Unicode block names. |

> Tip: There are a number of great resources for regular expressions on the internet that you can refer to for formulating character-based regex patterns for searching, for example http://regexlib.com/CheatSheet.aspx

# Custom Named Entities
The Named Entity Profiles option within the Global Options panel provides the ability to set the preferred entities to be used for consistent processing across cases. You can use industry-standard regular expressions in the data set and can enact profiles that have a set of these preferred entities for processing. It also shows improved performance by only selecting the named entities you wish to use.

The Custom Named Entities feature is available to users with a Case_Creation license using Workstation. The Nuix Data Finder (NDF) plugin requires the SENSITIVE_DATA_FINDER plus feature to be enabled. 

![Custom Named Entities](https://github.com/keerthipaddy/worksamples/blob/master/images/CNE_GLO.png)

## Creating Custom Named Entities
Navigate to Global Options and select Custom Named Entities to view the list editor. The Custom Named Entities option allows you to customize full regular expressions within Workstation. 

To add a new entity definition, click +. Select a scope for the new entry and click OK. The Create Entity Definition window is displayed with Entity Details and Test Entity tabs. The Entity Details tab enables you to create a new entity. 

![Entity Details](https://github.com/keerthipaddy/worksamples/blob/master/images/NEP.png)

| Option |	Description |
|------- | -----------|
|Set Entity Name and Description|  |
| Name | Enter a name for the Named Entity, ensuring it does not contain an asterisk (*).|*
| Icon | Browse and select an icon. The icon size needs to meet the specifications 48px by 48px or smaller. A default icon for an entity is used, if an icon is not provided.|
| Description |	Add a description for the Named Entity (optional). |
| Write Entity Pattern |  |
| Pattern	| Enter a valid regular expression pattern. Navigate to the Test Entity tab to validate the pattern and add it to the list. The default character length for the pattern is 256 characters. | 
| Import | Allows you to import a pattern from a file. |

The Test Entity tab enables you to test the entity pattern. In the Sample text field, enter the text you want to test. To import a sample text, click Import and browse to the location. Click Run test and the matches are shown in the Matches field. Clear clears the fields. Click OK to add the named entity to the list.  

When creating a named entity, a user can assign a .png file to be the icon. Otherwise, the default icon will be used. By default, a new search found in the Named Entities folder will be assigned a generic icon. For example, a search for Twitter handles could have a Twitter icon by editing the regex.properties file in the Named Entities directory to point to twitter.png. The regex.properties file also controls how the icons should be sectioned and what order they would appear in the Results Pane selection drop-down.

> Note: Ensure the Extract named entities from text, Include text stripped items, Extract named entities from properties options are enabled within the Evidence Processing Settings panel. Every time a named entity is added, reload the items on the results pane to view results.

# Named Entity Profiles
A Named Entity Profile provides the ability to set the preferred named entity/entities to be used for consistent processing across cases. It also shows improved performance by only selecting the named entities the users wish to use. 

![Named Entity Profile](https://github.com/keerthipaddy/worksamples/blob/master/images/NEP_GLO.png)

## Creating a Named Entity Profile
Navigate to Global Options and select Named Entity Profiles to view the list editor.
- To add and edit a named entity profile, select Named Entity Profiles from Global Options, click on the (+) sign to add a new named entity profile.
- To rename a profile, select the rename option from the list editor. Note that the name of the profile cannot be changed from the Modify Named Entity Profile window.
1. Select Named Entity Profiles from Global Options, click on the (+) sign to add a new named entity profile.
2. Select the scope for the entry and click OK. 
The Create Named Entity Profile window appears. 

![Create Named Entity Profile](https://github.com/keerthipaddy/worksamples/blob/master/images/NEP1.png)

3. In the Profile Details section, provide a name and a description for the Named Entity Profile.
4. In the Entities section, select/ search or filter for your preferred entity you want to add from the All Entities list. The selected entities appear within the Entities in Profile list. 
5. To remove an entity from the profile list, click remove (-). See notes on Remove/ Delete Entities and Profiles below for more information. 
6. Click OK to proceed.  

> Note: 
>
- While selecting the scope for Named Entity Profiles: 
- A User scope Named Entity Profile should have User scope and Local computer scope Custom Named Entities to select from.
- A Case scope Named Entity Profile should have Case, User, Local computer scope Custom Named Entities to select from.
- A Local scope Named Entity Profile should have only the Local computer scope Custom Named Entity to select from.
- The Case scope option appears only when the case is open.
- The Case scope Custom Named Entities must be present in the case for which the Custom Named Entities were created. 
- The Case scope Named Entity Profiles can only be used as an evidence processing settings. Case scope Named Entity Profiles cannot be added in a data processing profile.
- Named Entity Profiles can also be used directly as a data processing setting from the Advanced button while adding case evidence.
- Renaming a Named Entity Profile removes it from the selection: Once a Named Entity Profile is renamed, the profile must be selected within the Data processing settings, Use custom named entity profile drop-down option.
- Similarly, if the Named Entity profile is used in a Data Processing Profile, then the user will need to update the Data Processing Profile and select the renamed profile from the Add Case Evidence, Processing profile drop-down option.
- To remove or delete a named entity profile, click on the remove option and accept the confirmation message to remove the selected profile.
- If a profile selected for deletion is used for processing, then the processing will fail. Users are advised to verify before proceeding with the deletion of a named entity profile.
- Custom Named Entities will only be processed if they are added in a Named Entity Profile that is being used.
- If a Custom Named Entity is deleted within a profile, then all processing jobs using that profile will fail. In this case, the profile must be updated. 
- When you update the profile in Edit mode from Global options, the Entities in Profile list is automatically updated and the deleted Custom Named Entity is removed. Click OK. This ensures the profile can be used.
>
