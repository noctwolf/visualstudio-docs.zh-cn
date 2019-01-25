---
title: IPerPropertyBrowsing2 接口 1 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2 interface
ms.assetid: 1e50b3f7-cc1c-495a-93c7-3ee03aea0b8a
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bded7159b72fc8c1ae8408611ce858105e6734da
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344016"
---
# <a name="iperpropertybrowsing2-interface-1"></a>IPerPropertyBrowsing2 接口 1
访问属性页中的信息提供的对象。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|`GetDisplayString`|返回描述指定的属性的文本字符串。|  
|`MapPropertyToPage`|返回允许对操作的指定属性的属性页的 CLSID。|  
|`GetPredefinedStrings`|返回计数的字符串数组 (`LPOLESTR`指针) 列出了允许的值指定的属性可接受的说明。|  
|`SetPredefinedValue`|属性的值设置为令牌标识的预定义值 `dwCookie.`|  
  
## <a name="requirements"></a>要求  
 标头： dbgprop.h