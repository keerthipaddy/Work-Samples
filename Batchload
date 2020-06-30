---
layout: default
title: home
---

![This script was last tested in Nuix 7.8](https://img.shields.io/badge/Script%20Tested%20in%20Nuix-7.8-green.svg)

View the GitHub project [here](https://github.com/Nuix/Batch-Load-Report) or download the latest release [here](https://github.com/Nuix/Batch-Load-Report/releases).

# Overview

**Written By:** Keerthi

Generates a report with information about Nuix batch loads.  Report includes:

- Relevant Evidence 
- Batch Load Start 
- Batch Load Finish 
- Batch Load Elapsed 
- Items 
- Email Items 
- Calendar Items 
- Contact Items 
- Document Items 
- Spreadsheet Items 
- Presentation Items 
- Drawing Items 
- Other-document Items 
- Image Items 
- Multimedia Items 
- Database Items 
- Container Items 
- System Items 
- No-data Items 
- Unrecognised Items 
- Log Items 
- Chat-conversation Items 
- Chat-message Items

**Note:** To calculate elapsed time for a batch load, the script locates the corresponding history event in the case (which records a start and a stop time).  The time when a batch load completes loading and the stop time of the history event can slightly differ (so they don't always match exactly).  To address this, the script matches a batch load to its corresponding history event by finding the two with the smallest difference in time between [BatchLoadDetails.getLoaded](https://download.nuix.com/releases/desktop/stable/docs/en/scripting/api/nuix/BatchLoadDetails.html#getLoaded--) and [HistoryEvent.getEndDate](https://download.nuix.com/releases/desktop/stable/docs/en/scripting/api/nuix/HistoryEvent.html#getEndDate--).

In my testing this approach looks to work quite well.  The only instance I can think this may incorrectly match up the two is if multiple batch loads completed in a very small and similar span of time.  This is unlikely to be the case, with the only potential instance that I can think of this occurring being if a compound case contains multiple simple cases that contain batch loads that were processed concurrently.

**TL;DR** There is a potential for for the wrong elapsed time to be reported for a given batch load, although I believe the likelihood of this is rather low.

# Getting Started

## Setup

Begin by downloading the latest release of this code.  Extract the contents of the archive into your Nuix scripts directory.  In Windows the script directory is likely going to be either of the following:

- `%appdata%\Nuix\Scripts` - User level script directory
- `%programdata%\Nuix\Scripts` - System level script directory

## Cloning this Repository

This script relies on code from [Nx](https://github.com/Nuix/Nx) to present a settings dialog and progress dialog.  This JAR file is not included in the repository (although it is included in release downloads).  If you clone this repository, you will also want to obtain a copy of Nx.jar by either:
1. Building it from [the source](https://github.com/Nuix/Nx)
2. Downloading an already built JAR file from the [Nx releases](https://github.com/Nuix/Nx/releases)

Once you have a copy of Nx.jar, make sure to include it in the same directory as the script.

# License

```
Copyright 2019 Nuix

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
