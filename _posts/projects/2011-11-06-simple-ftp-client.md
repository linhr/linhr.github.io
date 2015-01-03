---
layout: project
title: "SimpleFTPClient"
date: 2011-11-06 00:00:00+0800
categories: projects
---

SimpleFTPClient is an FTP client application with user-friendly GUI. It is written in C#.

Here are the basic operations that SimpleFTPClient supports:

*   Uploading files
*   Downloading files
*   Renaming remote files
*   Deleting remote files
*   Creating remote directories

Multiple upload or download operations are queued and
handled one after another. The user can restart, pause or stop a file transfer process easily. Interrupted file transfers can be recovered later.

![SimpleFTPClient]({{ site.baseurl }}/images/projects/simple-ftp-client.png)

SimpleFTPClient supports PORT and PASV modes to avoid problems related to NAT or firewalls. The standard FTP commands supported by SimpleFTPClient are as follows:

*   `USER`, `PASS`, `CWD`, `QUIT`, `PORT`, `PASV`, `TYPE`, `RETR`, `STOR`, `REST`, `RNFR`, `RNTO`, `ABOR`, `DELE`, `RMD`, `MKD`, `PWD`, `LIST` and `NOOP` (defined in RFC 959)
*   `RETR` (for use in stream mode) and `SIZE` (defined in RFC 3659)

SimpleFTPClient was one of my course project for *Computer Networks* (Course Number: 44100113) at Tsinghua University in autumn 2011.
