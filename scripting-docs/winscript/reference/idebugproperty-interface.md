---
title: IDebugProperty 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugProperty interface
ms.assetid: 7e8f5341-23ef-4029-814d-f5c2307b9203
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 963b11a4760fad8086822f13db129fae76467802
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58145754"
---
# <a name="idebugproperty-interface"></a>IDebugProperty 接口
用于描述任何层次结构正在调试的实体的属性具有名称、 类型和值。 大多数情况下，`IDebugProperty`用于描述表达式计算、 语句评估或注册评估的结果。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugProperty`接口。  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugProperty::GetPropertyInfo](../../winscript/reference/idebugproperty-getpropertyinfo.md)|获取`DebugPropertyInfo`描述此 `IDebugProperty``.`|  
|[IDebugProperty::GetExtendedInfo](../../winscript/reference/idebugproperty-getextendedinfo.md)|获取在属性上的扩展的信息。|  
|[IDebugProperty::SetValueAsString](../../winscript/reference/idebugproperty-setvalueasstring.md)|从字符串中设置属性的值。|  
|[IDebugProperty::EnumMembers](../../winscript/reference/idebugproperty-enummembers.md)|枚举属性的成员。|  
|[IDebugProperty::GetParent](../../winscript/reference/idebugproperty-getparent.md)|获取属性的父级。|  
  
## <a name="requirements"></a>要求  
 标头： dbgprop.h