---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:00:10
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
title: Salesforce package.xml Auto Builder
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

* Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) To Build package.xml

> There are 2 ways to build package.xml 
> 1. Build From SFDC API.
> 2. Use local file to build package.xml.

# Build package.xml From Server

> Sublime-Menu :SFDC-XY > Package Builder > Build Package.xml From Server

![1539845253603](/blog/images/xytools_images/1539845253603.png)



You can build package.xml like below.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Package xmlns="http://soap.sforce.com/2006/04/metadata">

    <types>
        <members>*</members>
        <name>InstalledPackage</name>
    </types>
    <types>
        <members>*</members>
        <name>CustomLabels</name>
    </types>
    <types>
        <members>*</members>
        <name>StaticResource</name>
    </types>
   ............
   ............
   ............
   ............
   ............
   ............
   ............
   ............
    <types>
        <members>*</members>
        <name>Settings</name>
    </types>
    <version>42.0</version>
</Package>

```



# Build package.xml From Open Files

Example, Open `Account.object`,`Blog.page`,`BlogController.cls`,`Blog__c.object` in Sublime

![1539846980157](/blog/images/xytools_images/1539846980157.png)

> Sublime-Menu : SFDC-XY > Package Builder > Build package.xml From Open Files

You can build package.xml like below.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Package xmlns="http://soap.sforce.com/2006/04/metadata">

    <types>
        <members>Blog</members>
        <name>ApexPage</name>
    </types>
    <types>
        <members>BlogController</members>
        <name>ApexClass</name>
    </types>
    <types>
        <members>Account</members>
        <members>Blog__c</members>
        <name>CustomObject</name>
    </types>
    <version>42.0</version>
</Package>

```



# Summary

## Package Builder

### Build Package.xml From Server

`Package Builder > Build Package.xml From Server`
Export all package.xml from server

### Build Package.xml From Server From Open Files

```
Package Builder > Build Package.xml From Open Files
```

### Build The deploy package from open files

`Package Builder > Build Deploy Package From Open Files`
This is only copy the open files to a dir, not deploy to server.