---
categories:
- Salesforce
date: 2017-08-06 18:02:34
description: SFDC SalesforceXyTools Data Migrate
layout: post
tags:
- SFDC
- Salesforce
- Apex
- SalesforceXyTools
title: SFDC SalesforceXyTools Data Migrate 2
update_date: 2020/05/23 23:56:52

---

# How to migrate data between two Salesforce Organization ?

How to migrate data between Salesforce Organization ?
You can use dataloader download from Salesforce Organization 1,
and then upload to the Salesforce Organization 2.
This is the common way . But , it is slow.
Today I will introduce the new way for you.



# SFDC SalesforceXyTools Data Migrate 

You can use [SalesforceXyTools](https://chrome.google.com/webstore/detail/salesforce-xytools/ehklfkbacogbanjgekccnbfdgjechlmf?hl=ja) to Migrate Data between two Salesforce Organization.

## Open the Data Migration
Open the Data Migration Page as below.

- Setp1. Select Your Environment
- Setp2. Select Your SObject
- Organization1 Object
- Organization2 Object

![sfdc-salesforcexytools-data-migrate1](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate2-1.jpg)

## SOQL Builder
Insert Your SOQL
![sfdc-salesforcexytools-data-migrate2](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate2-2.jpg)

Run `Bulk Insert`, the soql will be run in organization1, and the data will be transfer to organization2 by bulk api.
Also, you can `Bulk Delete` data.
![sfdc-salesforcexytools-data-migrate5](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate5.jpg)

## Check Result.
Check the log,

Check the job in Organization2:
![sfdc-salesforcexytools-data-migrate7](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate7.jpg)

Check the data in Organization2:
![sfdc-salesforcexytools-data-migrate8](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate8.jpg)


# Install SalesforceXyTools For Chrome

<a target="_blank" class="btn" href="https://chrome.google.com/webstore/detail/salesforcexytools/ehklfkbacogbanjgekccnbfdgjechlmf?hl=ja">Install SalesforceXyTools For Chrome From Web Store</a>