---
ref: board-connector-08
layout: page
title: Logging
description: Logging
product: board-connector
parent: board-connector
childidentifier: logging
permalink: /:collection/:path
weight: 8
lang: en_GB
old_url: /BOARD-Connector-EN/default.aspx?pageid=logging
---
BOARD Connector logs all steps performed on a system in log files. 
The log files are stored in the product directory <br>
e.g.,: `C:\Program Files\BOARDConnector\logs`

Different types of log files are created.


|Type | Name | Description | Location path |
|:------ | :------ |:--- | :--- |
|Server| ServiceLog.txt | Contains the activities of BCService.exe.| `C:ProgramFiles\BOARDConnector\logs` |
|Server| ConfigServer-Log: yyyyMMddTHHmmss.fffZ.log, e.g., 20201013T055455.465Z.log | The name contains the timestamp in UTC. A new file is created when the server is started, additionally a new log file is created every 24 hours. BCConfigServer.exe is the corresponding process.| `C:ProgramFiles\BOARDConnector\logs\server\config` |
|Server| WebServer-Log: yyyyMMddTHHmmss.fffZ.log, e.g., 20201013T055455.465Z.log  | The name contains the timestamp in UTC. A new file is created when the server is started, additionally a new log file is created every 24 hours. BCWebServer.exe is the corresponding process.| `C:ProgramFiles\BOARDConnector\logs\server\web` |
|Server| Run-Logs: yyyyMMddTHHmmss.fffZ.log, e.g., 20201013T055455.465Z.log  | The name contains the timestamp in UTC. A new file is created when a TCP connection is accepted.BCRun.exe is the corresponding process.| `C:ProgramFiles\BOARDConnector\logs\server\run` |  
|Extraction| Extraction logs: yyyyMMddTHHmmss.fffZ.log, e.g., 20201013T055455.465Z.log | The name contains the timestamp in UTC. A new file is created to start an extraction. BCRun.exe is the corresponding process.|  `C:\Program Files\BOARDConnector\logs\extractions\[Name_der_Extaktion]`|

### Log Levels
Each log entry is assigned to a so-called log level. There are the following log levels:

- **Errors** are error messages issued during the extraction process.
- **Information** - Status messages, about processes that do not lead to an error.
- **Warnings** - Information about problems that do not lead to an extraction error. For example authentication errors.
- **Debug Details** - detailed information that helps to find the reason for errors.

### Reading Logs - Extraction Log

![View-Extraction-Log](/img/content/View-Extraction-Log.png){:class="img-responsive"} 
Select the check boxes in the upper left corner to decide which log levels to display.

To better understand the procedures of BOARD Connector, you can read the logs written in understandable language.
The [example of a readable log](https://help.theobald-software.com/en/xtract-universal/logging#reading-logs---extraction-log) can be taken from Xtract Universal as the procedures are similar. The only difference is that BOARD Connector does not have destinations and data is always written to BOARD. 

{% include _content/table-of-contents.html parent=page.childidentifier collection=site.en %}