---
categories:
- Salesforce
date: 2017-07-29 18:02:34
description: SFDC SalesforceXyTools Data Migrate
layout: post
tags:
- SFDC
- Salesforce
- Apex
- SalesforceXyTools
title: SFDC SalesforceXyTools Data Migrate
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

## Step1. Open the Query(Data Migrate)
Open the Query(Data Migrate) Page as below.
![sfdc-salesforcexytools-data-migrate1](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate1.jpg)

## Step2. Input your soql in organization1
Input your soql, and run it.
![sfdc-salesforcexytools-data-migrate2](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate2.jpg)

Check your data.
![sfdc-salesforcexytools-data-migrate3](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate3.jpg)

## Step3. Select your Organization2
![sfdc-salesforcexytools-data-migrate4](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate4.jpg)

Run `Bulk Insert`, the soql will be run in organization1, and the data will be transfer to organization2 by bulk api.
Also, you can `Bulk Delete` data.
![sfdc-salesforcexytools-data-migrate5](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate5.jpg)

## Step4. Check Result.
Check the log as below:
![sfdc-salesforcexytools-data-migrate6](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate6.jpg)

Check the job in Organization2:
![sfdc-salesforcexytools-data-migrate7](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate7.jpg)

Check the data in Organization2:
![sfdc-salesforcexytools-data-migrate8](/blog/images/salesforcexytools-for-chrome/sfdc-salesforcexytools-data-migrate8.jpg)


# Install SalesforceXyTools For Chrome

<a target="_blank" class="btn" href="https://chrome.google.com/webstore/detail/salesforcexytools/ehklfkbacogbanjgekccnbfdgjechlmf?hl=ja">Install SalesforceXyTools For Chrome From Web Store</a>