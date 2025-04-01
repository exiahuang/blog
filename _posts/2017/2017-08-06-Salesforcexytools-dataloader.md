---
categories:
- Salesforce
date: 2017-08-06 18:03:34
description: Use Salesforcexytools dataloader to auto backup salesforce.
layout: post
tags:
- SFDC
- Salesforce
- Apex
- SalesforceXyTools
title: Use Salesforcexytools dataloader to auto backup salesforce.
update_date: 2020/05/23 23:56:51

---

# Use Salesforcexytools dataloader to auto backup salesforce.

## Install Java and ant.
Salesforcexytools-Dataloader is base on Ant and dataloader,
Please install ant and java.

1. Make sure you have a Java environment installed, See System Requirements for details.
2. Download Ant. See Binary Edition for details.
3. Uncompress the downloaded file into a directory.
4. Set environmental variables `JAVA_HOME` to your Java environment, `ANT_HOME` to the directory you uncompressed Ant to, and add `${ANT_HOME}/bin` (Unix) or `%ANT_HOME%\bin` (Windows) to your PATH. See Setup for details.
5. Optionally, from the ANT_HOME directory run ant -f fetch.xml -Ddest=system to get the library dependencies of most of the Ant tasks that require them. If you don't do this, many of the dependent Ant tasks will not be available. See Optional Tasks for details and other options for the -Ddest parameter.
6. Optionally, add any desired Antlibs. See Ant Libraries for a list.


# How to Backup salesforce Data.

## Open Schema Page

![SalesforeXyTools-Dataloader](/blog/images/salesforcexytools-for-chrome/SalesforeXyTools-Dataloader-1.jpg)

## Download SalesforceXyTools-Dataloader

![SalesforeXyTools-Dataloader](/blog/images/salesforcexytools-for-chrome/SalesforeXyTools-Dataloader-2.jpg)

![SalesforeXyTools-Dataloader](/blog/images/salesforcexytools-for-chrome/SalesforeXyTools-Dataloader-2.1.jpg)

## Download Build.xml
Click `Create Build.xml`
![SalesforeXyTools-Dataloader](/blog/images/salesforcexytools-for-chrome/SalesforeXyTools-Dataloader-3.jpg)

If you want to backup all the data from your sfdc, you can download all sobjcet backup config.
Please click `Create Build.xml(All Sobjcet)`.

## Copy Build.xml file to [SalesforeXyTools-Dataloader]
 Copy Build.xml file to [SalesforeXyTools-Dataloader]
![SalesforeXyTools-Dataloader](/blog/images/salesforcexytools-for-chrome/SalesforeXyTools-Dataloader-4.jpg)

## Config your user and password.
![SalesforeXyTools-Dataloader](/blog/images/salesforcexytools-for-chrome/SalesforeXyTools-Dataloader-5.jpg)

※How to create your password.
[Create the Encrypted Password](https://developer.salesforce.com/docs/atlas.en-us.dataLoader.meta/dataLoader/command_line_create_enc_password.htm)

## Run in windows
Just click `run.bat`.
Or
```
Ant all
```

## Run in Mac/Linux
```
Ant all
```