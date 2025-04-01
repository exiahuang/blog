---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:00:13
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
title: Soql Creator
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

* Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) To Create soql

# Environment

- Make sure you can login your sfdc. Test it : SFDC-XY > Login SFDC


# Create Soql

`SFDC Code Creator > Create Soql`

![1540459992691](/blog/images/xytools_images/1540459992691.png)

Select Soql Type

![1540460017305](/blog/images/xytools_images/1540460017305.png)



result :

```sql
select 
			Id,				//カスタムオブジェクト ID
			OwnerId,				//所有者 ID
			IsDeleted,				//削除
			Name,				//ブログNo
			RecordTypeId,				//レコードタイプ ID
			CreatedDate,				//作成日
			CreatedById,				//作成者 ID
			LastModifiedDate,				//最終更新日
			LastModifiedById,				//最終更新者 ID
			SystemModstamp,				//System Modstamp
			LastViewedDate,				//最終閲覧日
			LastReferencedDate,				//最終参照日
			comment__c,				//評価
			comment_status__c,				//評価ステータス
			content__c,				//内容
			excerpt__c,				//概要
			status__c,				//ステータス
			title__c,				//タイトル
			ReadOnlyTest__c,				//ReadOnlyTest
			FormulaTest__c,				//数式テスト
			Account__c				//取引先
from Blog__c

```