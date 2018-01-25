---
layout: default
title:  sfdc-queue-max-size
date:   2018-01-25 22:11:04 +0900
categories: sfdc-queue-max-size
---

# トランザクション単位の Apex 制限
```
Maximum number of methods with the `future` annotation allowed per Apex invocation	`50`
Apex 呼び出し 1 回につき許可される `future` アノテーションを持つメソッドの最大数	`50`

Maximum number of Apex jobs added to the queue with `System.enqueueJob`	`50`
`System.enqueueJob` によってキューに追加される Apex ジョブの最大数	`50`
```

# find the max size
{% highlight java %}
public class QueueMaxSize {
   
    public static void sleep(integer milliseconds) {
        if(milliseconds == null) return;
        
        Long timeDiff = 0;
        DateTime firstTime = System.now();
        do {
            timeDiff = System.now().getTime() - firstTime.getTime();
        }
        while(timeDiff <= milliseconds);      
    }
    
    public class QueueSample implements Queueable, Database.AllowsCallouts{ 
        String name;
        
        public QueueSample(String name){
            this.name = name;
        }
        
        public void execute(QueueableContext context) {
            System.debug('>>>queue execute : ' + name);
            integer milliseconds = 10*60*1000;
            QueueMaxSize.sleep(milliseconds);
            System.debug('>>>done');
        }
    
    }
    
    public static void run(){
        for(Integer i = 1 ; i < 1000; i++){
            ID jobID = System.enqueueJob(new QueueSample('' + i));
            System.debug('jobID : ' + jobID);
        }
    }
    
}
{% endhighlight %}

Run QueueMaxSize 
```
QueueMaxSize.run();
```

# result:
![Queue-Max-Size]({{ "/pic/sfdc/queue-max-size.png" | prepend: site.baseurl }})

# Apex CPU time limit exceeded	
 CPU time is calculated for all executions on the Salesforce application servers occurring in one Apex transaction. 
 CPU time is calculated for the executing Apex code, 
 and for any processes that are called from this code, 
 such as package code and workflows. 
 CPU time is private for a transaction and is isolated from other transactions. 
 Operations that don’t consume application server CPU time aren’t counted toward CPU time. 
 For example, the portion of execution time spent in the database for DML, SOQL, and SOSL isn’t counted, 
 nor is waiting time for Apex callouts.
 
![Queue-Max-Size]({{ "/pic/sfdc/apex-cpu-limit.png" | prepend: site.baseurl }})
