---
categories:
- Salesforce
date: 2017-04-14 23:06:18
description: SalesforceXyTools Online Introduce，SalesforceXyTools再线讲座
layout: post
tags:
- SFDC
- Salesforce
- Apex
- SalesforceXyTools
title: SalesforceXyTools Online Introduce
update_date: 2020/05/23 23:56:51

---

# SalesforceXyTools Online Introduce

* [salesforcexytools for chrome 详细使用说明](http://salesforcexytools.com/Salesforce/SalesforceXyTools-For-Sublime.html) 
* [salesforcexytools for sublime 详细使用说明](http://salesforcexytools.com/Salesforce/SalesforceXyTools-For-Sublime.html) 
* [QA](#QA)

# What is SalesforceXyTools For Chrome

<div class="note primary">SalesforceXyTools Chrome插件
- 一键登录Force.com
- 快速检索Sobject,Apex,Trigger,Page,Component,EmailTemplate,SataticResource,数据列表
- 自动生成Soql， 执行soql， soql检索历史记录
- 执行Apex Script代码
- 快速检索SFDC文档
- 执行Rest Api
- 察看代码覆盖率Code Coverage
- 支持JSForce Script
</div>

## Install SalesforceXyTools For Chrome

<a target="_blank" class="btn" href="https://chrome.google.com/webstore/detail/salesforcexytools/ehklfkbacogbanjgekccnbfdgjechlmf?hl=ja">Install SalesforceXyTools For Chrome From Web Store</a>

## MainMenu， Document Search
  ![SalesforceXyToolsForChrome](/blog/images/salesforcexytools-for-chrome/salesforcexytools-for-chrome1.jpg) 

## SOQL Creator, Tooling Query Creator
  ![SalesforceXyToolsForChrome](/blog/images/salesforcexytools-for-chrome/salesforcexytools-for-chrome5.jpg) 
  ![SalesforceXyToolsForChrome](/blog/images/salesforcexytools-for-chrome/salesforcexytools-for-chrome6.jpg) 

## Run Apex Script
  ![SalesforceXyToolsForChrome](/blog/images/salesforcexytools-for-chrome/salesforcexytools-for-chrome7.jpg) 

## Run JSForce Script

example

```js
var records = [];
conn.query("SELECT Id, Name FROM Account", function(err, result) {
  if (err) { return console.error(err); }
  console.log("total : " + result.totalSize);
  console.log("fetched : " + result.records.length);
});
```

  ![SalesforceXyToolsForChrome](/blog/images/salesforcexytools-for-chrome/saleforcexytools-for-chorme-run-jsforce.jpg) 


# What is SalesforceXyTools For Sublime

<div class="note primary">SalesforceXyTools Sublime插件
- 生成Apex Test Class Code,生成Test Data
- 导出Sobject Excel表
- 父子关系SQOL生成
- DAO,DTO,VF,Controller生成
</div>


## Install
1. Open Sublime Text 3
2. Run `Package Control: Install Package` command
3. Search for `SalesforceXyTools`
4. Hit `Enter`, That is all.

## Config SalesforceXyTools For Sublime
略过。。。

## SalesforceXyTools Export Soject To Excel
  ![SalesforceXyToolsForSublimeHelp](/blog/images/salesforcexytools-for-sublime/ExportToExcel005.jpg) 
  ![SalesforceXyToolsForSublimeHelp](/blog/images/salesforcexytools-for-sublime/ExportToExcel006.jpg) 

## 测试代码生存
[SFDC-XY]->[SFDC Code Creator]->[Create Test Code]
![SalesforceXyToolsForSublimeHelp](/blog/images/salesforcexytools-for-sublime/Image001.jpg) 
  
## Auto Create VF-Controller-DTO-DAO-Code
1. 针对Object生成相关代码， 增删查改等操作，列表，明细。
2. Run `Package Control: Install Package` command
3. 演示效果

### 列表编辑页面
  ![SalesforceXyToolsForSublimeHelp](/blog/images/salesforcexytools-for-sublime/SaleforceXyTools-Help005.jpg) 

### 列表确认页面
  ![SalesforceXyToolsForSublimeHelp](/blog/images/salesforcexytools-for-sublime/SaleforceXyTools-Help006.jpg) 

### 详细编辑页面
  ![SalesforceXyToolsForSublimeHelp](/blog/images/salesforcexytools-for-sublime/SaleforceXyTools-Help007.jpg) 

### 详细确认页面
  ![SalesforceXyToolsForSublimeHelp](/blog/images/salesforcexytools-for-sublime/SaleforceXyTools-Help008.jpg) 

# QA