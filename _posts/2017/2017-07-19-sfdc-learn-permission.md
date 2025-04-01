---
categories:
- Salesforce
date: 2017-07-19 08:05:34
description: SFDC learn permission
layout: post
tags:
- SFDC
- Salesforce
- Apex
title: SFDC learn permission Edit Read Only Fields
update_date: 2020/05/23 23:56:51

---

# Problem : Read-only not working
I have a custom object where I don't want users to edit any fields.  I've made these all Read-Only in the Page Layout, but when I test the page I can still edit these fields by double-clicking and then saving.  I've verified that I'm using the correct Page Layout.  Any thoughts?

# Answer
If you are administrator you will still be able to edit the fields. If you REALLY want to make sure the fields can't be edited change the permissions on the field level security (you can do this by going into the setup menu, selecting the field and then clicking the view security button) rather than on the page layout.

# Some Usefull QA
1. Are you testing this with a `Sys Admin` profile? Do take note that sys admins have Edit `Read Only fields` permission by default. So even if a field is `Read only`, an Admin with this permission would still be able to edit them.
2. If you are testing this with your new custom profile, you may want to double check that `these permissions` have been taken off or not
3. `Page layout assignment` - Since you have made the fields as `Read Only` at the page layout level, please check if you have the right page layout assigned to the profile that you are using to test this out

# Edit Read Only Fields 参照のみ項目の編集
`参照のみ項目の編集`

![参照のみ項目の編集](/blog/images/sfdc-image/EditReadOnlyFields.png)