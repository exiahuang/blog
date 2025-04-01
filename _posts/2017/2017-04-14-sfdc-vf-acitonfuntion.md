---
categories:
- Salesforce
date: 2017-04-14 22:15:34
description: SFDC VF ActionFunction
layout: post
tags:
- SFDC
- Salesforce
- Apex
title: SFDC VF ActionFunction
update_date: 2020/05/23 23:56:53

---

# SFDC VF ActionFunction

<a target="_blank" class="btn" href="https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_js_remoting_compare_actionfunction.htm">Comparing JavaScript Remoting and actionFunction</a>

<a target="_blank" class="btn" href="https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_js_remoting_example.htm">JavaScript Remoting Example</a>

* The <apex:actionFunction> tag:
    * lets you specify rerender targets
    * submits the form
    * doesn’t require you to write any JavaScript
* JavaScript remoting:
    * lets you pass parameters
    * provides a callback
    * requires you to write some JavaScript


## explain 1
<div class="note primary">You must specify a rerender attribute in the `<apex:actionFunction>` tag! Without this the generated function does take any parameters, but as soon as you put it in then it does - even if you just leave it empty, i.e. the below code will generate doStuff(x) {...} Go figure.</div>

```html
<apex:actionFunction name="doStuff" action="{!myAction}" rerender="">  
  <apex:param name="x" value="x" assignTo="{!m_x}"/>
</apex:actionFunction>
```

## explain 2

<div class="note primary">ActionFunctionのレンダリングプロパティの記述がないとパラメータがどう頑張っても渡らないのです。つまり</div>

```html
<apex:pageBlock id="rerenderPlace">
    <apex:actionFunction name="debug" action="{!controllerMethod}" rerender="rerenderPlace">
           <apex:param assignTo="{!stringVar}" name="first" value=""/>
    </apex:actionFunction>

    <apex:commandButton onclick="debug()">
</apex:pageBlock>
```

<div class="note primary">つまりというか、rerenderしないとパラメータ渡せないようです。
元々rerenderありきのタグなんでしょうかね。</div>


## explain 3
  ![SFDC VF actionfunction](/blog/images/sfdc-actionfunction/actionfunction.jpg) 

## How Can I pass parameters using apex:actionFunction??
<div class="note primary">There is an example for you</div>

```js
<apex:inputHidden value="{!param}" id="tmpNo"></apex:inputHidden>
<script language="javascript">
    function changeCategory(tmpVal) {
        document.getElementById('{!$Component.tmpNo}').value = tmpVal;
        changeCategory1(); //call actionfuntion
    }
</script>
```


# SFDC VF ActionSupport
```html
<apex:repeat value="{!bean.kinds}" var="kind">
    <apex:selectList id="kind" size="1" value="{!kind.value}">
        <apex:actionSupport action="{!doChangeKind}" event="onchange" rerender="frm">
            <apex:param assignTo="{!bean.kindNo}" value="{!kind.index}" name="kindNo"/>
        </apex:actionSupport>
        <apex:selectOptions value="{!kind.options}" />
    </apex:selectList>
</apex:repeat>
```