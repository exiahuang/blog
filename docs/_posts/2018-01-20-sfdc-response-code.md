---
layout: default
title:  sfdc-response-code
date:   2018-01-20 10:11:04 +0900
categories: salesforce sfdc apex
---

Salesforce apex response code: 

{% highlight java %}
global without sharing class MyRest {
@HttpGet 
    global static void get() {
        RestResponse res = RestContext.response;
        if (res == null) {
            res = new RestResponse();
            RestContext.response = res;
        }
        try {
            res.responseBody = Blob.valueOf(JSON.serialize(doGet()));
            res.statusCode = 200;
        } catch (EndUserMessageException e) {
            res.responseBody = Blob.valueOf(e.getMessage());
            res.statusCode = 400;
        } catch (Exception e) {
            res.responseBody = Blob.valueOf(
                    String.valueOf(e) + '\n\n' + e.getStackTraceString()
                    );
            res.statusCode = 500;
        }
    }
private static Object doGet() {
        ...
    }
}

{% endhighlight %}
