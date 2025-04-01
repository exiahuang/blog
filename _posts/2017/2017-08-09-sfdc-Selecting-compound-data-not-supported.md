---
categories:
- Salesforce
date: 2017-08-09 08:01:34
description: Salesforce Selecting compound data not supported in Bulk Query
layout: post
tags:
- SFDC
- Salesforce
- Apex
title: Salesforce Selecting compound data not supported in Bulk Query
update_date: 2020/05/23 23:56:52

---

There isn't much out there on this error.  Before doing any data update, I like to export the target object's full data set as a precaution.  My tool of choice is workbench but sometimes it can be a little baby and complain like "Selecting compound data not supported in Bulk Query". 

![Error](/blog/images/sfdc-image/bulk-api-error.jpg)

Turns out that the following fields are going to make your bulk api export fail:


Address fields like:
    Billing Address
    Shipping Address
Latitude and Longitude fields like:
    BillingLatitude
    BillingLongitude


These are your most common "compound" fields.  Once you remove these fields from your export, you should be ok.

[Source](https://developer.salesforce.com/docs/atlas.en-us.api.meta/api/compound_fields.htm)