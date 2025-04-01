---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:00:09
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
title: Use SalesforceXytoolsForSublime Salesforce Deploy Package
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

* Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) To Build Salesforce Deploy Package

# Example

Example, Open `Account.object`,`Blog.page`,`BlogController.cls`,`Blog__c.object` in Sublime

![1539846980157](/blog/images/xytools_images/1539846980157.png)

> Sublime-Menu : SFDC-XY > Package Builder > Build Deploy package From Open Files
>
> Input your save path

You can build package.xml like below.

```
src
  │  package.xml
  │
  ├─classes
  │      BlogController.cls
  │      BlogController.cls-meta.xml
  │
  ├─objects
  │      Account.object
  │      Blog__c.object
  │
  └─pages
          Blog.page
          Blog.page-meta.xml
```



about package.xml

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