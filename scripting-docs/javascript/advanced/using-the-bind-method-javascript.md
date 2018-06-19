---
title: 使用 bind 方法 (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- bind method [JavaScript]
- this object [JavaScript]
ms.assetid: f608f95b-3b9d-437a-a67a-5a4ef8f6c07f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d185801cc5bba355751147edb79b9c47d21f8eed
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2018
ms.locfileid: "28987862"
---
# <a name="using-the-bind-method-javascript"></a>使用 bind 方法 (JavaScript)
JavaScript `bind` 方法具有几种用法。 通常，它用于为在其他上下文中执行的函数保留执行上下文。 `bind` 创建具有与原始函数相同的主体的新函数。 传递给 `bind` 的第一个参数指定绑定函数中的 `this` 关键字的值。 也可以将其他可选参数传递到 `bind`。 有关其他用法的示例，请参阅 [bind 方法（函数）](../../javascript/reference/bind-method-function-javascript.md)。 有关使用 `bind` 部分应用函数的示例，请参阅 [Hilo JavaScript 中的异步编程模式和提示（Microsoft Store）](http://msdn.microsoft.com/library/windows/apps/jj649740.aspx)。  
  
## <a name="preserving-the-execution-context-using-bind"></a>使用 bind 保留执行上下文  
 通常，在添加事件侦听器时使用 `bind` 函数。 在下面的代码示例中，`bind` 用于保留当前对象 (`DataObject`) 的上下文。 通过使用 `bind` 关键字将数据对象传递到 `this`，这可在事件处理程序 (`dataReadyHandler`) 运行时提供对数据对象属性和函数的访问。 为了阐释 `bind` 的工作原理，此代码会创建自定义事件。  
  
```JavaScript  
var data;  
  
var dataReadyEvent = document.createEvent("Event");  
dataReadyEvent.initEvent("dataReady", true, false);  
  
function DataObject() {  
    this.name = "Data Object";  
    this.data = function () {  
        return data;  
    }  
    this.onDataCompleted = dataReadyHandler;  
    document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
    // To see the result of not using bind, comment out the preceding line,   
    // and uncomment the following line of code.  
    // document.addEventListener('dataReady', this.onDataCompleted);  
}  
function dataReadyHandler() {  
    if (console && console.log) {  
        console.log("Data object property value: " + this.name);  
        console.log("Data object property value: " + this.data());  
    }  
}  
  
setTimeout(function () {  
    data = [0, 1, 2, 3];  
    document.dispatchEvent(dataReadyEvent);  
    }, 5000);
  
var dataObj = new DataObject();  
  
// Output:  
// Data Object  
// 0,1,2,3  
  
```  
  
 如果注释掉使用 `bind` 的代码行，取消注释调用不带 `addEventListener` 的 `bind` 的代码行，然后重新运行此代码，则 `dataReadyHandler` 函数将失败。 例如，在 `dataReadyHandler` 中，`this.name` 将是未定义的，并且 `this.data()` 将导致发生错误，因为 `this` 对象不再引用此数据对象。  
  
## <a name="see-also"></a>请参阅  
 [bind 方法 (Function)](../../javascript/reference/bind-method-function-javascript.md)
