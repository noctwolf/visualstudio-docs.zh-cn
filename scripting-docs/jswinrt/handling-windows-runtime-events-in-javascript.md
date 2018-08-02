---
title: 在 JavaScript 中处理 Windows 运行时事件 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime events
- Windows Runtime events [JavaScript]
ms.assetid: d9436aff-2c30-4846-b8df-eaa3e63fd75c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f7e5780a2462e8980c22c474ae6236c87aee599b
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302801"
---
# <a name="handling-windows-runtime-events-in-javascript"></a>在 JavaScript 中处理 Windows 运行时事件
Windows 运行时事件在 JavaScript 中的表示方式与它们在 C++ 或 .NET Framework 中的表示方式不同。 它们不是类属性，而是表示为传递到类的 `addEventListener` 和 `removeEventListener` 方法的（小写）字符串标识符。 例如，可以通过将字符串“replacementchanged”传递给 `Geolocator.addEventListener` 方法来为 [Geolocator.PositionChanged](https://msdn.microsoft.com/library/windows/apps/xaml/windows.devices.geolocation.geolocator.positionchanged.aspx) 事件添加事件处理程序：  
  
```JavaScript  
var locator = new Windows.Devices.Geolocation.Geolocator();  
locator.addEventListener(  
    "positionchanged",   
     function (ev) {  
        console.log("Got event");  
    });  
```  
  
 也可以设置 `locator.onpositionchanged` 属性：  
  
```JavaScript  
locator.onpositionchanged =    
    function (ev) {  
        console.log("Got event");  
    };  
```  
  
.NET/C++ 和 JavaScript 的另一个区别是事件处理程序采用的参数数量。 在 .NET/C++ 中，一个处理程序采用两个参数：事件发送方和事件数据。 在 JavaScript 中，这两个参数捆绑为一个 `Event` 对象。 在以下示例中，`ev` 参数同时包含事件发送者（`target` 属性）和事件数据属性（此处仅为 `position`）。 事件数据属性是那些针对每个事件编档的参数。
  
```JavaScript  
function (ev) {  
    console.log("Sender: " + ev.target);  
    console.log("Position: " +  
        ev.position.latitude + "," +  
        ev.position.longitude);  
};  
```  
  
> [!IMPORTANT]
>  Windows 运行时功能不适用于在 Internet Explorer 中运行的应用。  
  
## <a name="see-also"></a>请参阅  
 [在 JavaScript 中使用 Windows 运行时](../jswinrt/using-the-windows-runtime-in-javascript.md)
