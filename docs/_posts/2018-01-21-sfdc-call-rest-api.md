---
layout: default
title:  sfdc-call-rest api
date:   2018-01-21 13:11:04 +0900
categories: salesforce sfdc apex
---

# Understanding the Web Server OAuth Authentication Flow
![Salesforce-Oauth-Flow]({{ "/pic/sfdc/oauth-flow.png" | prepend: site.baseurl }})

[Understanding the Web Server OAuth Authentication Flow](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/intro_understanding_web_server_oauth_flow.htm)

# get token

```
grant_type=password&client_id={client_id}&client_secret={client_secret}&username={username}&password={password}
```

```
Content-Type：application/x-www-form-urlencoded
```

# call rest api
```
Authorization：　Bearer + token
Content-Type :  application/json
```

REST API URL
https://instance.salesforce.com/services/apexrest/ServiceName/


# Using cURL in the REST Examples

Example:
```
curl https://***instance_name***.salesforce.com/services/data/v42.0/ 
-H "Authorization: Bearer 00D50000000IehZ\!AQcAQH0dMHZfz972Szmpkb58urFRkgeBGsxL_QJWwYMfAbUeeG7c1E6
LYUfiDUkWe6H34r1AAwOR8B8fLEz6n04NPGRrq0FM"
```

Enclose the session ID within single quotes. For example:
```
curl https://***instance_name***.salesforce.com/services/data/v42.0/ 
-H 'Authorization: Bearer sessionID'
```
