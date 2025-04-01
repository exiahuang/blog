---
categories:
- SalesforcexytoolsForSublime
date: 2019/01/04 12:00:00
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
title: Lightning Web Components HelloWorld
typora-copy-images-to: images/xytools_images/
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

In this project, you’ll:

- Install Sublime and [Salesforcexytools](http://salesforcexytools.com/SalesforcexytoolsForSublime/SalesforceXytoolsForSublime-001-Install.html).
- Set up your `java` and `ant` environment.
  - [Auto config salesforce ant-migration-tools](http://salesforcexytools.com/SalesforcexytoolsForSublime/SalesforceXytoolsForSublime-007-Migration-Tool.html)
- Create and deploy a Lightning web component.

# Config Salesforcexytools
[How to Config Salesforcexytools](http://salesforcexytools.com/SalesforcexytoolsForSublime/SalesforceXytoolsForSublime-002-Config.html).

Please set your api `45.0`

![1545965650321](/blog/images/xytools_images/1545965650321.png)




# Create a Hello World Lightning Web Component

## create a Lightning web component.

The Source is From [Create a Hello World Lightning Web Component](https://trailhead.salesforce.com/ja/content/learn/projects/quick-start-lightning-web-components/create-a-hello-world-lightning-web-component)

Create source in sublime, like below:

![1545964554803](/blog/images/xytools_images/1545964554803.png)

`helloWorld.html`

```html
<template>
    <lightning-card title="HelloWorld" icon-name="custom:custom14">
        <div class="slds-m-around_medium">
            <p>Hello, {greeting}!</p>
            <lightning-input label="Name" value={greeting} onchange={changeHandler}></lightning-input>
        </div>
    </lightning-card>
</template>
```



`helloWorld.js`

```javascript
import { LightningElement, track } from 'lwc';
export default class HelloWorld extends LightningElement {
    @track greeting = 'World';
    changeHandler(event) {
        this.greeting = event.target.value;
    }
}
```

`helloWorld.js-meta.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata" fqn="helloWorld">
  <apiVersion>45.0</apiVersion>
  <isExposed>true</isExposed>
  <targets>
    <target>lightning__AppPage</target>
    <target>lightning__RecordPage</target>
    <target>lightning__HomePage</target>
  </targets>
</LightningComponentBundle>
```



## Deploy a Lightning web component

Right Click -> Deploy Directory To Server

![1545965045120](/blog/images/xytools_images/1545965045120.png)

Select Deploy Direcotry

![1545965073324](/blog/images/xytools_images/1545965073324.png)

Click `Yes!`

![1545965134397](/blog/images/xytools_images/1545965134397.png)

Check the log 

![1545965313466](/blog/images/xytools_images/1545965313466.png)



# Add Component to App in Lightning Experience

Please read [Create a Hello World Lightning Web Component](https://trailhead.salesforce.com/ja/content/learn/projects/quick-start-lightning-web-components/create-a-hello-world-lightning-web-component)



# Resources

[Introducing Lightning Web Components](https://developer.salesforce.com/blogs/2018/12/introducing-lightning-web-components.html)


[Quick Start: Lightning Web Components](https://trailhead.salesforce.com/ja/content/learn/projects/quick-start-lightning-web-components)