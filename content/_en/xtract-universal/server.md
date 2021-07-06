---
ref: xtract-universal-07
layout: page
title: Server
description: Server
product: xtract-universal
parent: xtract-universal
childidentifier: server
permalink: /:collection/:path
weight: 30
lang: en_GB
old_url: /Xtract-Universal-EN/default.aspx?pageid=server
---

The follwing section contains an overview of the Xtract Universal server.

The server performs two main tasks:

- Run extractions stored in the [Config](./advanced-techniques/backup-and-migration#configuration-files) directory. 
- Make extractions stored in the [Config](./advanced-techniques/backup-and-migration#configuration-files) directory available to the Designer.

### Run Extraction on the Server

Execution is triggered by an HTTP request. The HTTP request can be triggered from the target environment for [pull destinations](./destinations#pull-and-push-destinations) or from the xu command line tool (xu.exe /xu.elf), see [Execute and Automate Extractions](./execute-and-automate-extractions). 

1. XtractRun.exe checks the authentication and authorization of the request.
2. The target environment is prepared for writing the extracted data (e.g. establish database connection, create file).
3. The license is checked.
4. A connection to the SAP system defined in the source is established.
5. The data of the defined extraction type is requested.
6. Each extracted data package is written to the target environment.
7. After all packages are received, XtractRun.exe terminates the connection to the SAP system and informs the target environment that the extraction is complete.

{: .box-tip }
**Tip:** The XtractRun.exe logs its actions in log files. 
The log files are located in the logs subdirectory of the program directory:`C:ProgramFiles\XtractUniversal\logs\server\run` (default) 
The logs can also be displayed in the Designer under **[Server]>[Logs (Run)]**, see [Extraction Logs](./logging/logging-access-via-designer#extraction-logs).

### Access the Settings using the Designer

1. Theobald.Xu.Rpc.Worker.exe checks the authentication and authorization of the request.
2. Designer requests a certain setting, e.g., list of all extractions. 
3. Theobald.Xu.Rpc.Worker.exe reads the requested settings from the [Config directory](./advanced-techniques/backup-and-migration#configuration-files) and sends these settings to the Designer.
4. The user changes the settings in the Designer (e.g., destination settings).
5. Designer sends the changed settings back to Theobald.Xu.Rpc.Worker.exe. Theobald.Xu.Rpc.Worker.exe saves the changed settings in the [Config directory](./advanced-techniques/backup-and-migration#configuration-files).

{: .box-tip }
**Tip**: The Theobald.Xu.Rpc.Worker.exe logs its actions in log files.
The log files are located in the logs subdirectory of the program directory: `C:\Program Files\XtractUniversal\logs\server\rpc\worker` (default).

### Server Architecture

The server runs as a Windows Service and the main process of the XU Service is XtractService.exe. The Windows Service can be [managed](./server/start-server) via the Windows Services administration or the Task Manager.

XtractService.exe starts two listener processes:
- XtractWebServer.exe
- Theobald.Xu.Rpc.Listener.exe

The both listener processes listen on the [Ports](./server/ports) defined in the [Server Settings](./server/server-settings).

{: .box-tip }
**Tip**: The XtractService.exe logs its actions in ServiceLog.txt 
The log file is located in the logs subdirectory of the program directory: `C:ProgramFiles\XtractUniversal\logs` (default).

#### Theobald.Xu.Rpc.Listener.exe
Theobald.Xu.Rpc.Listener.exe waits for new connection requests from the Designer. <br>
For each TCP connection the Theobald.Xu.Rpc.Listener.exe starts a new instance of Theobald.Xu.Rpc.Worker.exe, which processes all Designer requests coming in over the particular TCP connection, see [Access the Settings using the Designer](#access-the-settings-using-the-designer).

{: .box-tip }
**Tip:** The Theobald.Xu.Rpc.Listener.exe logs its actions in log files. 
The log files are located in the logs subdirectory of the program directory: `C:\ProgramFiles\XtractUniversal\logs\server\rpc\listener` (default).

#### XtractWebServer.exe
XtractWebServer.exe waits for HTTP requests. <br>
For each TCP connection the XtractWebServer.exe starts a new instance of XtractRun.exe, which processes all HTTP requests coming in over the particular TCP connection, see [Run Extraction on the Server](#run-extraction-on-the-server).

The following HTTP requests are possible:
- Executing an extraction
- Emptying the result cache of an extraction
- Canceling all runs of an extraction
- REST API requests e.g., [Logs](./logging/logging-access-via-http), [Metadata](./advanced-techniques/metadata-access-via-http) etc.

{: .box-tip }
**Tip:** The XtractWebServer.exe logs its actions in log files. 
The log files are located in the logs subdirectory of the program directory: `C:ProgramFiles\XtractUniversal\logs\server\web` (default).

*****
More information about the server can be found in the following sections:

{% include _content/table-of-contents.html parent=page.childidentifier collection=site.en %}
