---
title: IDebugPropertyEnumType_All 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugPropertyEnumType_All
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugPropertyEnumType_All interface
ms.assetid: 4d0f4fd5-e5f7-47cb-b746-860d6363e2cd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dc5bb84125ca0bf3b25f8f9b8cfe1dad6aeb6d9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097001"
---
# <a name="idebugpropertyenumtypeall-interface"></a>IDebugPropertyEnumType_All 接口
`IDebugPropertyEnumType`接口定义，以便其 Iid 的每个可以作为一个筛选器，传递`IDebugProperty::EnumMembers`请求相应的枚举器时。  
  
## <a name="syntax"></a>语法  
  
```cpp
IDebugPropertyEnumType_All : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugPropertyEnumType_All::GetName](../../winscript/reference/idebugpropertyenumtype-all-getname.md)|返回描述名称的文本字符串|  
  
 以下接口继承自`IDebugPropertyEnumType_All`，并没有更多的方法。  
  
```cpp
IDebugPropertyEnumType_Arguments : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_Locals : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_LocalsPlusArgs : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_Registers : IDebugPropertyEnumType_All  
```  
  
## <a name="see-also"></a>请参阅  
 [IDebugProperty::EnumMembers](../../winscript/reference/idebugproperty-enummembers.md)