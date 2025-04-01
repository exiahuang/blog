---
categories:
- SalesforcexytoolsForSublime
date: 2018/10/27 22:10:02
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
title: Salesforce test code creator
typora-copy-images-to: images/xytools_images
typora-root-url: ./
update_date: 2020/05/23 23:56:51

---

# Topic

* Use [SalesforceXytoolsForSublime](http://salesforcexytools.com/categories/SalesforcexytoolsForSublime/) To write a test class.

> 1. Auto Create test class.
> 2. Soql to apex code.
>

# Environment

- Make sure you can login your sfdc. Test it : SFDC-XY > Login SFDC



# Write a test class

## Auto Create TestCode

> Tips: It just create the code in the localhost. It will not deploy to your sfdc server.

Open the apex code, Right click. 

sample code:

```java
/**
* @author huangxy
*/
public with sharing class BlogController extends SfdcXyController {

        // DTO Bean
        public BlogDto blogDto {get;set;}

        public BlogController() {
            search();
        }

        private void search(){
            String id = ApexPages.currentPage().getParameters().get('id');
            if(String.isBlank(id)){
                this.blogDto = new BlogDto();
            }else{
                this.blogDto = new BlogDto(BlogDao.getBlogById(id));
            }
        }

        /**
         * upsert Dto
         */
        public PageReference doSave() {
            Boolean result;

            Savepoint sp = Database.setSavepoint();
            try {
                upsert blogDto.getSobject();
                result = true;
            } catch(DMLException e) {
                Database.rollback(sp);
                System.debug('saveDto DMLException:' + e.getMessage());
                result = false;
            } catch(Exception e) {
                Database.rollback(sp);
                System.debug('saveDto Exception:' + e.getMessage());
                result = false;
            }
            return null;
        }

        /**
         * Go Next
         */
        public override PageReference doNext() {
            Boolean result = doCheck();
            setNextMode(result);
            return null;
        }

        /**
         * Go Back
         */
        public override PageReference doBack() {
            Boolean result = true; 
            setBackMode(result);
            return null;
        }

        /**
         * do Check
         */
        public override Boolean doCheck() {
            Boolean result = true;

            return result;
        }
}

```



Right click, `SFDC-XY Code Creator >Create test code`


![1540449212136](/blog/images/xytools_images/1540449212136.png)





It will be create a test class like this:

```java
/**
* @author huangxy
*/
@isTest
private class BlogControllerTest {

    /**
     * This is a test method for BlogController
     */
    static testMethod void test_BlogController() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

		BlogController blogController = new BlogController();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for doSave
     */
    static testMethod void test_doSave() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

		BlogController blogController = new BlogController();
		PageReference resultDoSave = blogController.doSave();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for doNext
     */
    static testMethod void test_doNext() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

		BlogController blogController = new BlogController();
		PageReference resultDoNext = blogController.doNext();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for doBack
     */
    static testMethod void test_doBack() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

		BlogController blogController = new BlogController();
		PageReference resultDoBack = blogController.doBack();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for doCheck
     */
    static testMethod void test_doCheck() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

		BlogController blogController = new BlogController();
		Boolean resultDoCheck = blogController.doCheck();


        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


    /**
     * This is a test method for all
     */
    static testMethod void test_all() {

        // PageReference pageRef = Page.Blog;
        // Test.setCurrentPage(pageRef);
        // pageRef.getParameters().put('param1', 'param1');

        Test.startTest();

		//  test BlogController
		BlogController blogController = new BlogController();

		//  test doSave
		PageReference resultDoSave = blogController.doSave();

		//  test doNext
		PageReference resultDoNext = blogController.doNext();

		//  test doBack
		PageReference resultDoBack = blogController.doBack();

		//  test doCheck
		Boolean resultDoCheck = blogController.doCheck();



        Test.stopTest();

        // Check
        // System.assert(ApexPages.hasMessages());
        // for(ApexPages.Message msg : ApexPages.getMessages()) {
        //     System.assertEquals('Upload file is NULL', msg.getSummary());
        //     System.assertEquals(ApexPages.Severity.ERROR, msg.getSeverity());
        // }
    }


}

```

## Insert test data from Soql

Insert Test Data(From SOQL)

Input a soql query string.

```sql
select id,name,comment__c,content__c from Blog__c limit 2
```

![1540449792963](/blog/images/xytools_images/1540449792963.png)



Right click, `SFDC-XY Code Creator > Insert Test Data(From Soql)`

![1540449870938](/blog/images/xytools_images/1540449870938.png)

The sql will be change to apex code like below.

   ```java
        List<Blog__c> blogList = new List<Blog__c>();
        Blog__c blog0 = new Blog__c();
        // blog0.id = 'a006F00002pzN2TQAU';    // カスタムオブジェクト ID
        blog0.name = 'ID-0013';   // ブログNo
        // blog0.comment__c = '';    // 評価
        blog0.content__c = 'test 承認プロセステスト';   // 内容
        blogList.add(blog0);
        
        Blog__c blog1 = new Blog__c();
        // blog1.id = 'a006F00002k90XhQAI';    // カスタムオブジェクト ID
        blog1.name = 'ID-0000';   // ブログNo
        blog1.comment__c = '11';   // 評価
        blog1.content__c = 'AHVI0uh0';   // 内容
        blogList.add(blog1);
        
        upsert blogList;
   ```

## Insert random test data 

Right click, `SFDC-XY Code Creator > Insert Test Data(All Field)` or

`SFDC-XY Code Creator > Insert Test Data(Needed Field)`

![1540457409043](/blog/images/xytools_images/1540457409043.png)

Select your sobject, It will create code like below.

```java
List<Blog__c> blogList = new List<Blog__c>();
for(Integer i=0; i<5; i++){
	Blog__c blog = new Blog__c();
	blog.RecordTypeId = recordtypeidList[i].id;    //レコードタイプ ID
	blog.comment__c = '3VG5bF0' + string.valueof(i) ;    //評価
	blog.comment_status__c = 'approve';    //評価ステータス
	blog.content__c = '6p8psSh' + string.valueof(i) ;    //内容
	blog.excerpt__c = 'YLpQQAw' + string.valueof(i) ;    //概要
	blog.status__c = 'Draft';    //ステータス
	blog.title__c = 'ot9xvaa' + string.valueof(i) ;    //タイトル
	blog.ReadOnlyTest__c = 'ld9IPfB' + string.valueof(i) ;    //ReadOnlyTest
	blog.Account__c = accountList[i].id;    //取引先
	blogList.add(blog);
}
insert blogList;


```