---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:00:02
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
title: How to Config SalesforceXytoolsForSublime
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# How to Config

[SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/)

## New Project

![1539934585052](/blog/images/xytools_images/1539934585052.png)

![1539934552300](/blog/images/xytools_images/1539934552300.png)



## Config Project

Project Setting > Project Config Wizard

![1539934605982](/blog/images/xytools_images/1539934605982.png)



* Select Sandbox Or Product
* Input your username
* Input your password
* Input your security_token. If you haven't security_token, let it blank
* Select your API Version

![1539934624694](/blog/images/xytools_images/1539934624694.png)



## Proxy Config

Project Setting > Proxy Config Wizard
![1539934831888](/blog/images/xytools_images/1539934831888.png)


# Start to develop sfdc
## Login Test
SFDC > Login SFDC

## Retrieve Metadata

![1539934961510](/blog/images/xytools_images/1539934961510.png)



Select metadata to retrieve

![1540365204093](/blog/images/xytools_images/1540365204093.png)



And Click `Start To Retrive`

# Modify the config file.

You also can modify the config file in `/.xyconfig/xyconfig.json`.
You can use `Project Settings > Open Project Config File`.
Each project has a config file.

```
{
    "username": "input your username",
    "password": "input your password",
    "security_token": "",
    "is_sandbox": true,
    "api_version": 40.0,
    "src_dir": "src",
    "authentication": "password", 
    "jar_home": "C:\\Users\\exia\\salesforce-project\\jar", 
    "use_os_terminal": false, 
    "auto_save_to_server": false,
    "app" : {
        "winmerge": "C:\\Program Files (x86)\\WinMerge\\WinMergeU.exe", 
        "notepad": "C:\\Program Files (x86)\\Notepad++\\notepad++.exe {file_name}",
        "Bash" : "cmd /k cd /d {file_dir}"
    },
    "default_browser": "chrome", 
    "browsers": {
        "chrome": "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe", 
        "IE": "C:\\Program Files\\Internet Explorer\\iexplore.exe"
    }, 
    "debug_levels": {
        "Apex_Code": "DEBUG", 
        "Callout": "INFO", 
        "Workflow": "INFO", 
        "Apex_Profiling": "INFO", 
        "Validation": "INFO", 
        "DB": "Info", 
        "System": "DEBUG"
    },
    "proxy": {
        "use_proxy" : false,
        "proxyhost" : "127.0.0.1",
        "proxyport" : "8888",
        "proxyuser" : "proxyuser",
        "proxypassword" : "proxypassword"
    }
}
```



## Config your login Browser

Add your `browsers` setting as below.
You can use `Project Settings > Switch Broswer` to set your default browser.

```json
// Add your browser which you like!
// examle:
// "firefox":"Path of firefox!",
"browsers":
{
    "chrome": "C:\\Program Files\\Google\\Chrome\\Application\\chrome.exe",
    "IE": "C:\\Program Files\\Internet Explorer\\iexplore.exe",
    "Firefox": "C:\\Program Files\\Firefox.exe"
},
```



# Use Oauth2 to access sfdc.

If you want to use oauth2 to access salesforce, please click
`Project Settings > Change Authentication Type` to set your authentication type.