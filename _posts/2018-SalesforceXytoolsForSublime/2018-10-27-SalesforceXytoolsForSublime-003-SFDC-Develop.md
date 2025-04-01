---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:00:03
layout: post
postman-category:
- SalesforcexytoolsForSublime
postman-tag:
- SalesforcexytoolsForSublime
- mytools
- salesforce
- sfdc
tags:
- SalesforcexytoolsForSublime
- mytools
- salesforce
- sfdc
title: Use SalesforceXytoolsForSublime to develop SFDC
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

- Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) to develope sfdc

> 1. create/update/delete/refresh local file : ApexClass, ApexTrigger, ApexPage, ApexComponent
> 2. Diff between localhost and server
> 3. Open metadata in sfdc
> 4. Deploy  : ApexClass, ApexTrigger, ApexPage, ApexComponent, Lightning
> 5. Run Test Class

# Environment

- Make sure you can login your sfdc. Test it : SFDC-XY > Login SFDC

# Start Develope

## Create ApexClass

This is an example of batch apexclass.

### Step1. New ApexClass

Metadata > New ApexClass

![1540364550961](/blog/images/xytools_images/1540364550961.png)

> Tips : Create ApexClass, ApexTrigger, ApexPage, ApexComponent in the same way



### Step2. Select Apex template


![1540365063496](/blog/images/xytools_images/1540365063496.png)


> Tips: search batch

![1540365114644](/blog/images/xytools_images/1540365114644.png)

Input your batch name

```java
global class SampleBatch1 implements Database.Batchable<sObject> {
	
	String query;
	
	global SampleBatch1() {
		
	}
	
	global Database.QueryLocator start(Database.BatchableContext BC) {
		return Database.getQueryLocator(query);
	}

   	global void execute(Database.BatchableContext BC, List<sObject> scope) {
	
	}
	
	global void finish(Database.BatchableContext BC) {
		
	}
	
}
```

## Update ApexClass

Change your apexclass, 

Right click, `SFDC-XY Metadata` > `Save To Server` 

![1540365460463](/blog/images/xytools_images/1540365460463.png)



## Refresh From Server

Right click, `SFDC-XY Metadata` > `Refresh From Server` 

![1540366564885](/blog/images/xytools_images/1540366564885.png)



## Delete

Right click, `SFDC-XY Metadata` > `Delete this metadata(Danger)` 

![1540366621242](/blog/images/xytools_images/1540366621242.png)

It will pop up a dialog like this.

![1540366789444](/blog/images/xytools_images/1540366789444.png)



## Diff between localhost and server

### Config your Winmerge

`Project Setting` > `Open Project Config file`

![1540366215462](/blog/images/xytools_images/1540366215462.png)

set your `winmerge` like below.

```json
.......
	"app": {
        "Bash": "cmd /k cd /d {file_dir}", 
        "winmerge": "C:\\Program Files (x86)\\WinMerge\\WinMergeU.exe", 
        "notepad": "C:\\Program Files (x86)\\Notepad++\\notepad++.exe {file_name}"
    }, 
.......
```

### Diff source

Right click, `SFDC-XY Metadata` > `Diff with Server` 

![1540365783795](/blog/images/xytools_images/1540365783795.png)

![1540366115227](/blog/images/xytools_images/1540366115227.png)



if you do not set `winmerge`, it will use simple diff.

![1540366430051](/blog/images/xytools_images/1540366430051.png)



## Find your source in sfdc

Right click, `SFDC-XY Metadata` > `Save To Server` 

It will go to sfdc source page.

![1540365563010](/blog/images/xytools_images/1540365563010.png)



## Deploy To SFDC

> There are some different between **Deploy** and **save**.

Right click, `SFDC-XY Metadata` > `Deploy To Server(Ant Migration Tool)` 

![1540432504706](/blog/images/xytools_images/1540432504706.png)



There 4 ways to deploy to sfdc server.  If you select **check only** , it never actually saves to the server.

* Deploy Open Files To Server:

* Deploy Open Files To Server(check only):

* Deploy Current File To Server : `xxx.cls`

* Deploy Current File To Server : `xxx.cls`(check only)



![1540432580625](/blog/images/xytools_images/1540432580625.png)



## Deploy the folder

choose your folder or source in sublime folders, then right click.

Find the menu : `Sfdc-Xy > Deploy Directory To SFDC`

![1540445304166](/blog/images/xytools_images/1540445304166.png)



## Run Test Class

Right click, `SFDC-XY Run` > `Run Test Class` 

![1540442455878](/blog/images/xytools_images/1540442455878.png)








# Summary

## Project

### New Project

`Project > New Project`
Input your project directory, and create your sfdc project

### Switch Project

`Project > Switch Project`

### Retrieve Source

`Project > Retrieve Source`
Select metatdata type, and click `Start To Retrieve` to retrieve source.
The old source `src` directory will be remove to `src_backup`

### Retrieve Source zip

`Project > Retrieve Source.zip`
Input your project directory, and retrieve zip.

### Reload Metadata Cache

`Project > Reload Metadata Cache`
Not need to Reload Metadata Cache.

## Metadata

### Create ApexClass, ApexTrigger, ApexPage, ApexComponent

`Metadata > New ApexClass`
`Metadata > New ApexTrigger`
`Metadata > New ApexPage`
`Metadata > New ApexComponent`


### Refresh Source

`Metadata > Refresh From Server`

### Diff with Server

`Metadata > Diff with Server`
If you want to use `winmerge` to check the different between local and server,
Please config `/.xyconfig/xyconfig.json`, set `winmerge`.
If you set `winmerge` blank, it will diff in sublime.

> Tips: You must use `\\` if you use Windows, such as `"C:\\Program Files (x86)\\WinMerge\\WinMergeU.exe"`

### Save To Server

`Metadata > Save To Server`

### Deploy To Server

Please use Migration Tools to deploy sources.
`Migration Tool > Ant Migration Tool`