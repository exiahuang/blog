---
categories:
- Salesforce
date: 2017-10-24 08:02:34
description: Salesforce batch feture queueable
layout: post
tags:
- SFDC
- Salesforce
- Apex
title: Salesforce batch feture queueable
update_date: 2020/05/23 23:56:51

---

# batch
The default timeout is 10 seconds. A custom timeout can be defined for each callout. The minimum is 1 millisecond and the maximum is 120,000 milliseconds. See the examples in the next section for how to set custom timeouts for Web services or HTTP callouts.
The maximum cumulative timeout for callouts by a single Apex transaction is 120 seconds. This time is additive across all callouts invoked by the Apex transaction.


# Future Methods
A future method runs in the background, asynchronously. You can call a future method for executing long-running operations, such as callouts to external Web services or any operation you’d like to run in its own thread, on its own time. You can also make use of future methods to isolate DML operations on different sObject types to prevent the mixed DML error. Each future method is queued and executes when system resources become available. That way, the execution of your code doesn’t have to wait for the completion of a long-running operation. A benefit of using future methods is that some governor limits are higher, such as SOQL query limits and heap size limits.

To define a future method, simply annotate it with the future annotation, as follows.

# Future
Queueable Interface methods and Future methods are Asynchronous Apex Processes that add jobs to the job queue and each job runs when system resources become available, so it doesn’t delay the execution of the main Apex logic. They also share a benefit of having some higher governor limits than synchronous Apex, such as heap size limits (12 MB),  number of SOQL queries issued (200) and Maximum CPU time on the Salesforce servers (60k ms). But the Queueable interface methods are a step up from the future methods because they also come with these additional benefits (according to Salesforce release notes):
​
To define a future method, simply annotate it with the future annotation, as follows:-
 
```
global class FutureClass{

   @future
   public static void myFutureMethod(){  

        // Perform some operations

   }

}
```

NOTE :-

1) Methods with the future annotation must be static methods
2) can only return a void type
3) The specified parameters must be primitive data types, arrays of primitive data types, or collections of primitive data types
4) Methods with the future annotation cannot take sObjects or objects as arguments.
5) You can invoke future methods the same way you invoke any other method. However, a future method can’t invoke another future method
6) No more than 50 method calls per Apex invocation
7) Asynchronous calls, such as @future or executeBatch, called in a startTest, stopTest block, do not count against your limits for the number of queued jobs
8) The maximum number of future method invocations per a 24-hour period is 250,000 or the number of user licenses in your organization multiplied by 200, whichever is greater
9) To test methods defined with the future annotation, call the class containing the method in a startTest(), stopTest() code block. All asynchronous calls made after the startTest method are collected by the system. When stopTest is executed, all asynchronous processes are run synchronously


IMP:-
The reason why sObjects can’t be passed as arguments to future methods is because the sObject might change between the time you call the method and the time it executes. In this case, the future method will get the old sObject values and might overwrite them.  To work with sObjects that already exist in the database, pass the sObject ID instead (or collection of IDs) and use the ID to perform a query for the most up-to-date record. The following example shows how to do so with a list of IDs


Example of a future method that makes a callout to an external service. Notice that the annotation takes an extra parameter (callout=true) to indicate that callouts are allowed
 
```
global class FutureMethodExample{

   @future(callout=true)
   public static void getStockQuotes(String acctName){  

        // Perform a callout to an external service

   }
}
```


# Queueable Interface

Getting an ID for your job: When you submit your job by invoking the System.enqueueJob method, the method returns the ID of the new job. This ID corresponds to the ID of the AsyncApexJob record. You can use this ID to identify your job and monitor its progress, either through the Salesforce user interface in the Apex Jobs page, or programmatically by querying your record from AsyncApexJob.
Chaining jobs: You can chain one job to another by starting a second job from a running job. Chaining jobs is useful if you need to do some processing that depends on another process to have run first.


Below is an example of how to implement the Queueable interface.
 
```
public class AsyncExecutionExample implements Queueable {

     public void execute(QueueableContext context) {

         Account a = new Account(Name='Acme',Phone='(415) 555-1212');

         insert a;

    }

}
```

You can add the class to a job queue by calling this method.
```
ID jobID = System.enqueueJob(new AsyncExecutionExample());
```

If you have a second class that also implements the Queueable interface and you want it to run after the class above is done, you can chain them together like this:
 
```
public class AsyncExecutionExample implements Queueable {
     public void execute(QueueableContext context) {
          Account a = new Account(Name='Acme',Phone='(415) 555-1212');
          insert a;
         // Chain this job to next job by submitting the next job
         System.enqueueJob(new SecondJob());
     }
}
```

# batch , future , queueable
## 1.The Batchable Interface
 • When should you use it? -
Complex long running processes (thousands of records)
- Asynchronous processing - Scheduled jobs
• How can you define a Batch? - Implement Database.Batchable -
Define start(), execute() and finish() methods

The Batchable Interface
• Advantages -
It can process up to 50m records
It can be scheduled to run at a particular time
• Disadvantages - Only five concurrent batch jobs running at a time* - It’s difficult to troubleshoot - Execution may be delayed based on server availability -
@future methods are not allowed - Can’t use getContent/getContentAsPDF methods - and a few more governor limits…

## 2. @future method • 
When should I use it?
 - When it’s not a batch (group = 2 or more) - Asynchronous processing (simple and often)
- Long-running operations (callouts to external web services) - Separating mixed DML operations
• How can I define @future method?
 - @future annotation - Must be static and return void - Specify (callout=true) to allow callouts
@future method
• Advantages - Asynchronous processing without a concurrent limit (queue)
- Easier and quicker to implement as opposed to Batch
- Can use getContent/getContentAsPDF methods
• Disadvantages - Parameters passed in can be only of Primitive type
 - - Can’t chain @future methods - Difficult access to job ID

## 3. The Queueable Interface
 • When should I use it?
 - When Batch and @future need to meet in the middle - Chaining jobs
 - You need @future method with support for non-primitive types
 - Asynchronous monitoring
 • How can I define Queueable Apex?
- Implement the Queueable interface - Define execute() method
• How can I enqueue a job? - ID jobID = System.enqueueJob(new MyQueueableClass());
The Queueable Interface • Advantages
 - Asynchronous processing with non-primitive arguments
- Easy access to the job ID - Chaining jobs* •
 Disadvantages - Can’t have more than one job in the chain that does callouts

Which one to use? Batchable @future Queueable
 - Good at processing large number of records (50m) and tasks are not time-crucial
 - Can be scheduled to run at a certain time 
- Maximum of 5 concurrent jobs running at a time 
- You need good error handling for troubleshooting 
- Quick async processing (typically one record at a time) e.g. avoid mixed DML or a web service callout - Faster than a Batch - Easy to implement
 - Only accepts primitive type arguments - Can’t chain jobs 
- Hard to monitor
 - Quick async processing that supports primitive types 
- Faster than a batch
 - Ability to chain jobs - Can’t have more than one job doing callouts within the chain - Can be monitored


# summary
![summary1](/blog/images/sfdc-image/sfdc-apex-batch-feture-queueable-1.png)
![summary2](/blog/images/sfdc-image/sfdc-apex-batch-feture-queueable-2.png)