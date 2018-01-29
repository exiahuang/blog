---
layout: default
title:  salesforce RecordType
date:   2018-01-29 22:15:04 +0900
categories: salesforce sfdc apex
---

What Doug B said is correct. RecordTypeId works for you because that's the actual field on Account. Its a lookup to RecordType, and as with all lookup fields in a trigger, to get the related value, you need to query for it.

However, you can probably get away with this, before your loop:

```
Map<ID, Schema.RecordTypeInfo> rtMap = Schema.SObjectType.Account.getRecordTypeInfosById();
```
And then inside your for loop do:
```
type = rtMap.get(o.RecordTypeId).getName();
```
