---
categories:
- Salesforce
date: 2017-07-08 08:02:34
description: Salesforce Web To Lead
layout: post
tags:
- SFDC
- Salesforce
- Apex
title: Salesforce Web To Lead
update_date: 2020/05/23 23:56:51

---

# WebToLead page

```html
<html>
	<head>
		<META HTTP-EQUIV="Content-type" CONTENT="text/html; charset=UTF-8">
	</head>
	<body>
		<form action="https://www.salesforce.com/servlet/servlet.WebToLead?encoding=UTF-8" target="_blank" rel="nofollow" method="POST">

			<input type=hidden name="oid" value="00DT0000000HRXp">
			<input type=hidden name="retURL" value="http://salesforcexytools.com" target="_blank" rel="nofollow" />
			<input type="hidden" name="debug" value=1>
			<input type="hidden" name="debugEmail" value="exia@salesforcexytools.com">
			<label for="first_name">First Name</label><input  id="first_name" maxlength="40" name="first_name" size="20" type="text" /><br>

			<label for="last_name">Last Name</label><input  id="last_name" maxlength="80" name="last_name" size="20" type="text" /><br>

			<label for="email">Email</label><input  id="email" maxlength="80" name="email" size="20" type="text" /><br>

			<label for="company">Company</label><input  id="company" maxlength="40" name="company" size="20" type="text" /><br>

			<label for="city">City</label><input  id="city" maxlength="40" name="city" size="20" type="text" /><br>

			<label for="state">State/Province</label><input  id="state" maxlength="20" name="state" size="20" type="text" /><br>

			<input type="submit" name="submit">

		</form>
	</body>
</html>
```


# call WebToLead 
https://test.salesforce.com/servlet/servlet.WebToLead?encoding=UTF-8&oid=00D0k0000000WpX&retURL=http://salesforcexytools.com&first_name=firstname&last_name=lastname

# web to lead
取引開始済みすると、もとの状態に戻れない
原因は下記です。。
![sfdc-lead](/blog/images/sfdc-image/sfdc-lead-fields.jpg)