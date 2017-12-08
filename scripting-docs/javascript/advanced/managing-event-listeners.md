---
title: "管理事件侦听器 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 87717f5d-b0c6-4c8d-a293-476002b7bfcf
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a97c579716b9964b8dfb93db419e9a70160d33a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="managing-event-listeners"></a>管理事件侦听器
如果 DOM 元素或对象的生存期不同于其关联事件侦听器的生存期，建议使用 [removeEventListener](http://msdn.microsoft.com/library/ie/ff975250\(v=vs.85\).aspx) 方法避免内存泄露。  
  
## <a name="event-listeners-and-object-scope"></a>事件侦听器和对象范围  
 下面的代码示例演示在调用 `dataObjFactory()` 函数时可能会导致内存泄露的代码。 在此代码中，在每次创建新数据对象时，将为数据对象注册一个事件侦听器。 为了使当前数据对象可用于 `dataReady()` 事件处理程序，在 `addEventListener` 中使用了 [bind 方法（函数）](../../javascript/reference/bind-method-function-javascript.md)。  
  
```JavaScript  
 var data;  
 var dataObj;  
  
 var dataReadyEvent = document.createEvent("Event");  
 dataReadyEvent.initEvent("dataReady", true, false);  
  
 function DataObject() {  
  
     this.name = "Data Object";  
     this.data = function () {  
         return data;  
     }  
     this.onDataCompleted = dataReady;  
     // this.handlerRef = this.onDataCompleted.bind(this);  
  
     // document.addEventListener('dataReady', this.handlerRef);  
     document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
 }  
  
 // Runs when the data is available.  
 function dataReady() {  
     if (console && console.log) {  
         console.log("object value: " + this.name);  
         console.log("object value: " + this.data());  
     }  
 }  
  
setTimeout(function () {  
    // Generate data after a timeout period.  
    data = [0, 1, 2, 3];  
    document.dispatchEvent(dataReadyEvent);  
}, 10000);  
  
function dataObjFactory() {  
     for (var x = 0; x < 100; x++) {  
         if (dataObj) {  
             // The following line of code has no effect.  
             document.removeEventListener('dataReady', dataObj.onDataCompleted);  
             dataObj = null;  
         }  
         dataObj = new DataObject();  
     }  
 }  
  
 dataObjFactory();  
```  
  
 每个数据对象的侦听器均在 `document` 对象（该对象具有与数据对象不同的生存期）中注册。 只要 `document` 对象仍保持在范围内，每个数据对象的已注册事件侦听器都会防止该对象被垃圾回收。 （在某些现代 JavaScript 设计模式中，文档对象在 Web 应用的生存期内将保留在范围中。）为了防止内存泄露，将在 `removeEventListener` 函数中调用 `dataObjFactory`。 但是，由于 `removeEventListener` 尚未在 `bind` 函数返回的事件处理程序的绑定版本上调用，此代码失败。  
  
 要修复此代码并使数据对象可供垃圾回收，你必须先存储一个对事件处理程序绑定版本的引用（如此代码中所示），然后将存储的引用传递到 `addEventListener`。 下面是 `DataObject` 的更正后代码：  
  
```JavaScript  
function DataObject() {  
  
    this.name = "Data Object";  
    this.data = function () {  
        return data;  
    }  
    this.onDataCompleted = dataReady;  
    this.handlerRef = this.onDataCompleted.bind(this);  
  
    document.addEventListener('dataReady', this.handlerRef);  
    // document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
}  
  
```  
  
 最后，你需要在绑定函数存储的引用 (`removeEventListener`) 上调用 `handlerRef`。 下面是 `dataObjFactory` 的更正后代码：  
  
```JavaScript  
function dataObjFactory() {  
     for (var x = 0; x < 100; x++) {  
         if (dataObj) {  
             document.removeEventListener('dataReady', dataObj.handlerRef);  
         }  
         dataObj = new DataObject();  
     }  
 }  
  
```  
  
 现在，对 `removeEventListener` 调用有效，并且不需要的数据对象可以进行垃圾回收，即使 `document` 对象仍在范围中也是如此。