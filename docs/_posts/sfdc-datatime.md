---
layout: default
title:  sfdc-datatime
date:   2018-01-20 10:11:04 +0900
categories: salesforce sfdc apex
---


{% highlight java %}
DateTime dt = (DateTime) JSON.deserialize('"2016-03-03T01:09:36.933"', DateTime.class);
System.debug('>>>>');
System.debug('>>>>' + dt); // 2016-03-03 06:09:36
System.debug('>>>>');
System.debug('>>>>' + dt.format('MM/dd/yyyy HH:mm')); // 03/03/2016 01:09

System.debug(DateTime.valueOfGmt(('06/08/2013 06:30:22').replaceAll('/','-')));

System.debug(DateTime.valueOfGmt('2013-08-06 06:30:22'));
System.debug(DateTime.valueOf('2013-08-06 06:30:22'));
System.debug(DateTime.parse('2013-08-06T06:30:22Z'));
System.debug(DateTime.parse('2013-08-06 06:30:22'));
{% endhighlight %}
