---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:00:14
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
title: Save Your Sfdc Module and build a deploy module package
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

* Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) To Save your sfdc module
* deploy module package

# Environment

- Make sure you can login your sfdc. Test it : SFDC-XY > Login SFDC

# Save a module

Open the source.

![1540519797063](/blog/images/xytools_images/1540519797063.png)

Right Click , `SFDC-XY Toolbox> Save Module(From Open Files)`

![1540519843822](/blog/images/xytools_images/1540519843822.png)

Input your save path

![1540519944813](/blog/images/xytools_images/1540519944813.png)

Check your module

![1540521537775](/blog/images/xytools_images/1540521537775.png)



# Deploy your module

## fix your target sfdc info
open `build.properties`

```properties
sf.username = {username}
sf.password = {password}
#sf.sessionId = <Insert your Salesforce session id here.  Use this or username/password above.  Cannot use both>
#sf.pkgName = <Insert comma separated package names to be retrieved>
#sf.zipFile = <Insert path of the zipfile to be retrieved>
#sf.metadataType = <Insert metadata type name for which listMetadata or bulkRetrieve operations are to be performed>

# Use 'https://login.salesforce.com' for production or developer edition (the default if not specified).
# Use 'https://test.salesforce.com for sandbox.
sf.serverurl = {serverurl}
sf.maxPoll = 500
sf.pollWaitMillis = 10000
# If your network requires an HTTP proxy, see http://ant.apache.org/manual/proxy.html for configuration.
#
```


## windows

only check your code:  click `deployCodeCheckOnly.bat` only!

deploy your code:  click `deployCodeRunLocalTests.bat` only!

## Linux/Mac

only check your code

```
ant deployCodeCheckOnly
```

deploy your code

```
ant deployCodeRunLocalTests
```