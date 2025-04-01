---
categories:
- Salesforce
date: 2017-04-26 22:30:34
description: Salesforce　Knowledge　Objects
layout: post
tags:
- SFDC
- Salesforce
- Apex
title: Salesforce　Knowledge　Objects
update_date: 2020/05/23 23:56:51

---

# Salesforce Knowledge Objects

<div class="note primary">This entity relationship diagram (ERD) illustrates relationships between the Salesforce Knowledge objects.
</div>

  ![Salesforce-Knowledge-Objects](/blog/images/sfdc-article/Salesforce-Knowledge-Objects.png)

# KnowledgeArticleVersion
```sql
SELECT Title
FROM KnowledgeArticleVersion
WHERE PublishStatus='Draft'
AND language ='en_US'
```

# KnowledgeArticle
```sql
SELECT Title
FROM Offer__kav
WHERE PublishStatus='online'
AND language ='en_US'
```

# learn more
[sforce_api_guidelines_knowledge](https://developer.salesforce.com/docs/atlas.en-us.api.meta/api/sforce_api_guidelines_knowledge.htm)