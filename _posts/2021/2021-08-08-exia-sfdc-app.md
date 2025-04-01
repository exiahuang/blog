---
categories: sfdx
date: 2021/08/08 14:33:23
layout: post
tags:
- sfdx
title: Exia Sfdc App
update_date: 2021/08/08 14:33:23

---



Thank you for reading this article. My name is Exiahuang. I had created some applicatons about sfdc. I will introduce to you in this article.



## Mobile App

### SF365:  Salesforce Android App

SF365:  Run your salesforce in mobile app: faster, easier.

[SF365: Salesforce client. - Google Play Download ](https://play.google.com/store/apps/details?id=com.sf365.app&hl=en_US&gl=US)

Feature:
- Sobject Manager.
- Run Visualforce app.
- View Report.
- File Manager: Upload with camera.
- Api Limit: View Sfdc api limit.
- Support Apple Map / Goolge Map.
- Support Product/Fullsand/Sandbox/DX scratch org/Developer edition.



![SF365-Menu](/blog/images/exia-sfdc-app/SF365-Menu.png)

![sf365-file-manager](/blog/images/exia-sfdc-app/SF365-File-Manager.png)







## Vscode Extension

### XyCode

[Xycode Feature:](https://marketplace.visualstudio.com/items?itemName=ExiaHuang.xycode)

- a lightweight and fast command executor for vscode. support docker, wsl, bash. config commad as a vscode plugin.

- Less than 100k.

- Integrated with system command and work with vscode.

- Support sfdx, it is a Rapid development tool for Salesforce SFDX Development. Metadata diff with server, retrieve standard sobject...

- Support Docker/WSL Develop.

  

Download:

- vscode-> extension -> search xycode
- [xycode - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ExiaHuang.xycode)



![Vscode-Xycode](https://raw.githubusercontent.com/exiahuang/xycode-doc/gh-pages/images/xysfdx-open-wsl.gif)



### xysfdx: Vscode SFDX Develope tools

[xysfdx Feature:](https://marketplace.visualstudio.com/items?itemName=ExiaHuang.xysfdx) 

- A rapid development tool for Salesforce SFDX Development. Support Docker/WSL !
- Less than 100k
- Support [Dataloader v40.0.0~v47.0.0](https://github.com/exiahuang/dataloader) Export/ExportAll/Insert/Update/Upsert/Delete.
- Support Docker to develope sfdx . Use exiasfdc/sfdx docker image, no need to config, just run it.
- Support using WSL/git bash/Msys2/MingW64/MingW32 to develope sfdx .
- Authenticated with oauth2.
- Retrieve Metadata by select.
- **Metadata diff with server**(any sfdc organization).
- Retrieve standard sobject.
- Open sfdc link easily.
- Open console easily.



Option Features

- support Username-Password OAuth Authentication .
- auto run .apex file after save.
- auto save to sfdc server
- deploy to any sfdc organization
- pretty code: pretty .cmp, .page, .component, .trigger, .cls file
- support base git command.
- support [exiahuang/sfdc-cli](https://github.com/exiahuang/sfdc-cli).



Download:

- vscode -> extension -> search xysfdc
- [xysfdx - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ExiaHuang.xysfdx)




![vscode-xysfdx](https://raw.githubusercontent.com/exiahuang/xycode-doc/gh-pages/images/xycode-sfdx-retrieve-meta.gif)



## Chrome Extension

###  SalesforceXyTools Chrome App

SalesforceXyTools for Chrome is a developer tools for Salesforce,SFDC,Force.com.

1. Login SFDC By 1 click
2. Quickly Search For Sobject,Apex,Trigger,Page,Component,EmailTemplate,SataticResource, etc
3. Auto Create Soql, Run Soql, Soql History
4. Run Apex Script.
5. Quick Search SFDC Document
6. Run Rest Query
7. View Apex Code Coverage, Run Test Class, Auto CreateTestCode!!
8. Run JSForce Script
9. Download CSV/Excel/Json...
10. Apex Log Viewer
11. Data Migrate Between two Organization (Bulk Api)
12. Export Schema To Excel/CSV/...
13. Code Creator(SOQL,DAT,DTO,CONST,VF-page,Controller,process-xml.conf,sdl...)

Download:

- [Salesforce XyTools - Chrome ウェブストア (google.com)](https://chrome.google.com/webstore/detail/salesforce-xytools/ehklfkbacogbanjgekccnbfdgjechlmf)
- https://chrome.google.com/webstore/detail/salesforce-xytools/ehklfkbacogbanjgekccnbfdgjechlmf

![Saleforcexytools Chrome APP](/blog/images/exia-sfdc-app/SalesforcexytoolsChrome.png)

### Adminite Chrome

Adminite Chrome App is base on [Adminite](https://github.com/omniphx/adminite), a ELECTRON app. I changed it to a chrome plugin.

Feature:

- Base on React and Ant Design
- SFDC Oauth2.0 Authentication
- Less then 4M

Download:

- [Adminite Chrome - Chrome ウェブストア (google.com)](https://chrome.google.com/webstore/detail/adminite-chrome/llbghhnehkkfjjjindnbkfadjcpaifhc)

- https://chrome.google.com/webstore/detail/adminite-chrome/llbghhnehkkfjjjindnbkfadjcpaifhc



Thank for:

Adminite Chrome App Copyright (c) 2021 [ExiaHuang](https://github.com/exiahuang/adminite)

[Adminite](https://github.com/omniphx/adminite): MIT License Copyright (c) 2021 Marty

![Adminite-Chrome](/blog/images/exia-sfdc-app/Adminite-Chrome.png)



## LWC Library

### lwc-rxjs

- [lwc-rxjs](https://github.com/exiahuang/lwc-rxjs) A reactive programming library for salesforce lwc.
- https://github.com/exiahuang/lwc-rxjs

### lwc-ramda

- [lwc-ramda](https://github.com/exiahuang/lwc-ramda) is ramda for salesforce lwc developer.
- https://github.com/exiahuang/lwc-ramda

### lwc-lodash

- [lwc-lodash](https://github.com/exiahuang/lwc-lodash) is lodash for salesforce lwc developer.

- https://github.com/exiahuang/lwc-lodash

### lwc-buffer

- [lwc-buffer](https://github.com/exiahuang/lwc-buffer) The buffer module from [node.js](https://nodejs.org/), for the lwc developer. Base on [buffer](https://github.com/feross/buffer).
- https://github.com/exiahuang/lwc-buffer



## Dataloader

### exiahuang/dataloader

[exiahuang/dataloader](https://github.com/exiahuang/dataloader) Features

- Need ant and java
- Support Windows/WSL/Linux/Mac.
- Dataloader version: 40.0.0~47.0.0
- Support Export/ExportAll/Insert/Update/Upsert/Delete
- Not need to install dataloader, auto download.
- Integrated with [exiahuang/xysfdx](https://github.com/exiahuang/xysfdx) for `vscode`



## SFDX Plugin

### sfdx-xy-plugin

[sfdx-xy-pulgin Feature](https://github.com/exiahuang/sfdx-xy-plugin)

- deploy metadata from git diff
- retrieve metadata by keyword
- bulk apex test runner  by keyword
- https://github.com/exiahuang/sfdx-xy-plugin

Install：

```sh
sfdx plugins:install sfdx-xy-plugin
```



## Docker



### exiahuang/xysfdx-docker

Github: https://github.com/exiahuang/xysfdx-docker

Docker Hub: https://hub.docker.com/r/exiasfdc/sfdx

- salesforce develope docker
- for [exiahuang/xysfdx](https://github.com/exiahuang/xysfdx).



## Others

###  SalesforceXyTools For Sublime

- Sublime Text 3 SFDC develop tools
- Document  http://salesforcexytools.com/SalesforceXyTools/SalesforceXyTools-For-Sublime/

Install:

​	Sublime -> Package Control: Install Package -> SalesforceXyTools



### sfdc-cli

Github:https://github.com/exiahuang/sfdc-cli

- Python3  sfdc metadata develop tools
- This is the command line app of [exiahuang/SalesforceXyTools](https://github.com/exiahuang/SalesforceXyTools).
- Integrate with [exiahuang/xysfdx](https://github.com/exiahuang/xysfdx), and run in vscode.

Install From Pip

```
pip3 install sfdc-cli
```



### lightning-ui

lightning-ui is base on [bootstrap3.3](https://getbootstrap.com/docs/3.3/) and [slds](https://www.lightningdesignsystem.com/getting-started). You can use it on your python/nodejs/ruby/java/dotnet project. I build [salesforcexytools.heroku.com](https://salesforcexytools.heroku.com/) by using Python(Flask) and this lightning-ui.

Github: https://github.com/exiahuang/lightning-ui

Example:

- http://salesforcexytools.com/lightning-ui/examples/
- http://salesforcexytools.com/lightning-ui/



### exiahuang/Cmder

Github: https://github.com/exiahuang/Cmder
Document: http://salesforcexytools.com/Cmder/

Cmder for Sublime Text run customer command, Cmder for Sublime Text run any command. You can use it to run any os command, such as python, java, ruby, go, c, c++, github, docker, heroku, etc.

