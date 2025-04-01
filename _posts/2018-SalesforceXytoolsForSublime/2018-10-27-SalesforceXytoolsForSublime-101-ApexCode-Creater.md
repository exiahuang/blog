---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:10:01
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
title: Auto Create Salesforce VisualForce Apex
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

* Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) To Auto Create VisualForce・Apex Controller・DTO・DAO

- Auto Build Detail Page
    - Record Input  Page
    - Record Review Form
    - Save the Record
- Auto Build Record List Page
    - List All Records.
    - Search Record
    - Mass Edit Records
    - Records Review Form 

# Environment

- Make sure you can login your sfdc. Test it : SFDC-XY > Login SFDC

# Auto Create VF-Controller-DTO-DAO-Code

> Tips: It just create the code in the localhost. It will not deploy to your sfdc server.

## Find the menu 

SFDC Code Creator > Create VisualForce/Controller/DTO/DAO Code

![1540444254303](/blog/images/xytools_images/1540444254303.png)

## Choose your Sobject.

I will select `Blog__c`.

![1540444395082](/blog/images/xytools_images/1540444395082.png)

About `Blog__c`:

![1540535859753](/blog/images/xytools_images/1540535859753.png)





## Select Custom Fields Or All Fields.

I will select `1.Custom fields Only(Exculde Validate)`.

![1540444454039](/blog/images/xytools_images/1540444454039.png)



When It is done , It will show the popup like below.

There are many source will be opened if you choose `ok`. 

![1540444924569](/blog/images/xytools_images/1540444924569.png)

You can find the source in `./src_sfdc_module/code-creator/src`

![1540445085932](/blog/images/xytools_images/1540445085932.png)



# Deploy the codes

choose the `src`, then right click, `Sfdc-Xy > Deploy Directory To SFDC`

![1540445304166](/blog/images/xytools_images/1540445304166.png)



> Tips : If you build a complex page , maybe you can not deploy correctly. Fix the codes, then deploy them.



# Run it

visit the visualforce page

## Detail Page.
* Record Input  Page
* Record Review Form
* Save the Record

Page URL :  https://{instance}.salesforce.com/apex/Blog

### Input Form

![1540536475265](/blog/images/xytools_images/1540536475265.png)


### Review Form
Input something, then click `next`, then it will go to `Review Form`

![1540536538782](/blog/images/xytools_images/1540536538782.png)

![1540536818611](/blog/images/xytools_images/1540536818611.png)

click `save`, you can save the data.


## Record List Page

* List All Records.
* Search Record
* Mass Edit Records
* Records Review Form 

URL : https://{instance}.salesforce.com/apex/BlogList

### List All Records

![1540537365308](/blog/images/xytools_images/1540537365308.png)


### Search Record
> Tips: The Picklist will be changed to filter.



Select the filter, and search the data.

![1540537722015](/blog/images/xytools_images/1540537722015.png)


![1540537883121](/blog/images/xytools_images/1540537883121.png)



### Mass Edit Records

Edit records , and click `next`

![1540538022704](/blog/images/xytools_images/1540538022704.png)

### Records Review Form

Go to the review form, and click `save` button.

![1540538069994](/blog/images/xytools_images/1540538069994.png)



Go back to the list page, check the result.

![1540538151435](/blog/images/xytools_images/1540538151435.png)