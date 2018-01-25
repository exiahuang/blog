---
layout: default
title:  salesforce回调函数和接口编程
date:   2018-01-25 22:15:04 +0900
categories: salesforce sfdc apex
---

# 回调函数：

所谓回调，就是客户程序C调用服务程序S中的某个函数A，然后S又在某个时候反过来调用C中的某个函数B，对于C来说，这个B便叫做回调函数。回调函数只是一个功能片段，由用户按照回调函数调用约定来实现的一个函数。回调函数是一个工作流的一部分，由工作流来决定函数的调用（回调）时机。一般说来，C不会自己调用B，C提供B的目的就是让S来调用它，而且是C不得不提供。由于S并不知道C提供的B姓甚名谁，所以S会约定B的接口规范（函数原型），然后由C提前通过S的一个函数R告诉S自己将要使用B函数，这个过程称为回调函数的注册，R称为注册函数。Web Service以及Java 的RMI都用到回调机制，可以访问远程服务器程序。回调函数包含下面几个特性：

1. 属于工作流的一个部分；
2. 必须按照工作流指定的调用约定来申明（定义）；
3. 他的调用时机由工作流决定，回调函数的实现者不能直接调用回调函数来实现工作流的功能； 

## 回调机制：

回调机制是一种常见的设计模型，他把工作流内的某个功能，按照约定的接口暴露给外部使用者，为外部使用者提供数据，或要求外部使用者提供数据。

## java回调机制：

软件模块之间总是存在着一定的接口，从调用方式上，可以把他们分为三类：同步调用、回调和异步调用。

* 同步调用：一种阻塞式调用，调用方要等待对方执行完毕才返回，它是一种单向调用；
* 回    调：一种双向调用模式，也就是说，被调用方在接口被调用时也会调用对方的接口；
* 异步调用：一种类似消息或事件的机制，不过它的调用方向刚好相反，接口的服务在收到某种讯息或发生某种事件时，会主动通知客户方（即调用客户方的接口）。
* 回调和异步调用的关系非常紧密：使用回调来实现异步消息的注册，通过异步调用来实现消息的通知。

# salesforce回调实例

{% highlight java %}
public class CallBackSample {

    public void run(){
        //创建调用者的实现类
        Another another = new Another();
        
        //将回掉接口注册到实现类中
        another.setCallback(new MyCallBack());
        
        another.doCallback();
    }
    
    public class MyCallBack implements Callback {
       public String callBack() {
            return 'you are a pig';
       }
        
    }
    
    public interface Callback {
       String callBack();
    }
   
    public class Another {
      private Callback callback;
      
      //调用实现类的方法
      public void setCallback(Callback callback) {
        this.callback = callback;
      }
      
      //业务需要的时候，通过委派，来调用实现类的具体方法
      public void doCallback(){
        System.debug('>>>>doCallback');
        System.debug(callback.callBack());
      }
    }
}
{% endhighlight %}

