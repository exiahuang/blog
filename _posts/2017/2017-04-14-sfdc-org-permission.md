---
categories:
- Salesforce
date: 2017-04-14 22:10:34
description: SFDC Org Permission,Saleforceの権限管理の基本概念
layout: post
tags:
- SFDC
- Salesforce
- Apex
title: SFDC Org Permission
update_date: 2020/05/23 23:56:51

---

# 権限管理入門

* プロファイル
* 権限セット
* 共有設定
    * 組織の共有設定
    * ロール階層
    * 共有ルール
    * 個別データの手動共有

# Saleforceの権限管理の基本概念

Salesforceは、利用ユーザ毎の機能制限や、お客様の業務に合わせ顧客・案件データのアクセス権を様々な形で制御することが可能です。

![SFDC Org Permission](/blog/images/sfdc-permission/sfdc-permission-01.jpg) 

# プロファイル（ユーザにどこまで行わせるか？）

![SFDC Org Permission](/blog/images/sfdc-permission/sfdc-permission-02.jpg) 

# 権限セット（ユーザにどこまで行わせるか？）

権限セットは、特定のユーザに、プロファイル+αで、権限を追加する場合に利用するものです。 プロファイルは、ユーザに`1つ`のみ割り当て可能ですが、権限セットは、ユーザに`複数`割り当てることが可能なため、より柔軟な権限設定が可能です。

権限セットを利用すると、プロファイルの設定を変更したり、複数のプロファイルを作成するといった工数を削減することが可能になります。

![SFDC Org Permission](/blog/images/sfdc-permission/sfdc-permission-03.jpg) 

# 共有設定（ユーザにどこまでのデータを見せる・変更させる？）

* 組織の共有設定
  * オブジェクト毎に、全ユーザの「他人のレコード」に対する共有アクセス権を設定
* ロール階層
  * 階層を使い、他人のレコードの共有アクセス権を設定
* 共有ルール
  * 階層型ではない特殊な共有アクセス権を設定
* 個別データの手動共有
  * 各レコード毎に共有先を自由に設定

![SFDC Org Permission](/blog/images/sfdc-permission/sfdc-permission-04.jpg) 

## 組織の共有設定
組織の共有設定・・・全ユーザに関わる基準となるアクセス権限
![SFDC Org Permission](/blog/images/sfdc-permission/sfdc-permission-05.jpg) 

## ロール階層
ロール階層・・・上位ユーザが下位ユーザのデータにアクセス可能
![SFDC Org Permission](/blog/images/sfdc-permission/sfdc-permission-06.jpg) 

## 共有ルール
共有ルール・・・特定のデータを特定のユーザに共有
![SFDC Org Permission](/blog/images/sfdc-permission/sfdc-permission-07.jpg) 

## 個別データの手動共有
手動共有・・・個々のデータレベルで共有

![SFDC Org Permission](/blog/images/sfdc-permission/sfdc-permission-08.jpg) 


# download pdf
<a target="_blank" class="btn" href="/images/sfdc-permission/権限管理入門_20120309.pdf">権限管理入門_20120309.pdf</a>