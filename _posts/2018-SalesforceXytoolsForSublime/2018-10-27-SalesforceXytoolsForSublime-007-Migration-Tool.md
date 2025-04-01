---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:00:07
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
title: Auto config salesforce ant-migration-tools and Backup Metadata
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

- Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) To Config ant-migration-tools and backup metadata.

> 1. Auto config ant-migration-tools.
> 2. Backup all salesforce metadata in one click. You do not need to config package.xml !



# Environment

* Set up your `java` and `ant` environment.
* You must install `java` and `ant` before use `ant dataloader`.
* You not need to Install the `dataloader`.
* Make sure you can login your sfdc. Test it : SFDC-XY > Login SFDC

# Auto Config ant-migration-tools

>  Sublime-Menu :SFDC-XY > Migration Tool > Ant Migration Tool

![1539848350521](/blog/images/xytools_images/1539848350521.png)

Select `Config Ant Metadata Tool`

![1540431779525](/blog/images/xytools_images/1540431779525.png)



# Backup all Metadata

>  Sublime-Menu :SFDC-XY > Migration Tool > Ant Migration Tool
>
>  Select `Backup All Metadata`

![1540431839856](/blog/images/xytools_images/1540431839856.png)



It will take some time to backup all sfdc metadata. It will backup to the `sfdc-xy\MetadataBackupTools\backup-metadata\`

![1540432165067](/blog/images/xytools_images/1540432165067.png)



>  Tips : It is base on [Ant Migration Tool ](https://developer.salesforce.com/docs/atlas.en-us.216.0.daas.meta/daas/meta_development.htm).



# Schedule Task , Auto Backup sfdc metadata.

You can find ant-migration-tools in `./sfdc-xy/MetadataBackupTools` Folder.

You don't need to config `package.xml`.

Just copy `MetadataBackupTools` and config your **system tasks**

![1539848747628](/blog/images/xytools_images/1539848747628.png)



## windows

In **windows**, you can set task like this.

![1539849119939](/blog/images/xytools_images/1539849119939.png)

![1539849440133](/blog/images/xytools_images/1539849440133.png)



## Unix cron

You can set your cron job in unix/ linux/ mac