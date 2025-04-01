---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:00:06
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
title: Auto config salesforce ant-dataloader and Backup Sobject Data
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

- Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) To Config Dataloader and backup sfdc sobject data.

> 1. Auto config dataloader.
> 2. Backup salesforce sobject data.

# Environment

- Set up your `java` and `ant` environment.
- You must install `java` and `ant` before use `ant dataloader`.
- You not need to Install the `dataloader`.
- Make sure you can login your sfdc. Test it : SFDC-XY > Login SFDC

> Tips : You not need to Install the dataloader, Salesforcexytools integrates with dataloader.

# Auto Config Dataloader

Open Sublime-Menu : SFDC-XY > Dataloader > Build Ant Dataloader Configuration

![1539931429520](/blog/images/xytools_images/1539931429520.png)



Select `Your Sobjects` and  Select `Start To Config`, example:

![1539931785518](/blog/images/xytools_images/1539931785518.png)



You can find **AntDataloader** in `./sfdc-xy/AntDataloader` Folder.

![1539931980132](/blog/images/xytools_images/1539931980132.png)



# Run AntDataloader

## Ant command

```
cd ./sfdc-xy/AntDataloader
ant
```



![1539932235973](/blog/images/xytools_images/1539932235973.png)



## Run in sublime

`Dataloader > Run Ant Dataloader`
The data will be export to `/sfdc-xy/AntDataloader/Export_YYYYMMDD_HHmm`

![1539932182175](/blog/images/xytools_images/1539932182175.png)



# config your soql

Open `./sfdc-xy/AntDataloader/build.xml`

Add your `export` task, you can export sfdc sobject data easily.

```xml
    <target name="start_export">
        <!-- <export file="{FILE_NAME}" object="{SOBJECT_NAME}" soql="{SOQL}"/> -->
        <export file="Blog__c" object="Blog__c" soql="SELECT Id , Name , Title__c, Body__c FROM Blog__c"/>
        <export file="Log__c" object="Log__c" soql="SELECT Id , Name, Body__c FROM Log__c"/>
    </target>
```



> Tips:  Config the `build.xml` and copy `Ant Dataloader` to anywhere, and add your schedule job to export sfdc data.



# Schedule Task , Auto Backup sfdc sobject data.

copy `./sfdc-xy/AntDataloader` To any folder. and schedule task.