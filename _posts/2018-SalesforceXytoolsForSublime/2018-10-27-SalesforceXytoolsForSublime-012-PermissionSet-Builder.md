---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:00:12
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
title: PermissionSet Builder
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

* Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) To Build fieldPermission and objectPermission

> 1. Build permissionset file
>

# Environment

- Make sure you can login your sfdc. Test it : SFDC-XY > Login SFDC


# Create Permission.xml

## Open SObject Manager Page

`Permission Builder> Build Profile FieldPermissions`

![1540457828769](/blog/images/xytools_images/1540457828769.png)

Select your field

![1540457987197](/blog/images/xytools_images/1540457987197.png)

The Permissionset file :
```xml
<?xml version="1.0" ?>
<PermissionSet xmlns="http://soap.sforce.com/2006/04/metadata">
  <fieldPermissions>
    <editable>true</editable>
    <field>Blog__c.comment__c</field>
    <readable>true</readable>
  </fieldPermissions>
  <objectPermissions>
    <allowCreate>true</allowCreate>
    <allowDelete>true</allowDelete>
    <allowEdit>true</allowEdit>
    <allowRead>true</allowRead>
    <modifyAllRecords>true</modifyAllRecords>
    <object>Blog__c</object>
    <viewAllRecords>true</viewAllRecords>
  </objectPermissions>
  <hasActivationRequired>false</hasActivationRequired>
  <label>AllPermission</label>
  <license>Salesforce</license>
</PermissionSet>
```

# Deploy permission.xml

right click , deploy it.