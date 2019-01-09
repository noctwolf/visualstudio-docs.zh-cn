---
title: DBGPROP_INFO_FLAGS |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DBGPROP_INFO_FLAGS
apilocation:
- scrobj.dll
f1_keywords:
- DBGPROP_INFO_FLAGS
helpviewer_keywords:
- DBGPROP_INFO_FLAGS
ms.assetid: e9450a21-a802-4c3e-8b3d-8e202f555de1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 517999bce9c85475bd91ad2e54e7ed49cda23aab
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095753"
---
# <a name="dbgpropinfoflags"></a>DBGPROP_INFO_FLAGS
用于指定`DebugPropertyInfo`字段  
  
## <a name="syntax"></a>语法  
  
```cpp
enum {  
   DBGPROP_INFO_NAME  =0x001,  
   DBGPROP_INFO_TYPE  =0x002,  
   DBGPROP_INFO_VALUE  =0x004,  
   DBGPROP_INFO_FULLNAME  =0x020,  
   DBGPROP_INFO_ATTRIBUTES  =0x008,  
   DBGPROP_INFO_DEBUGPROP  =0x010,  
   DBGPROP_INFO_AUTOEXPAND  =0x8000000  
};  
```  
  
## <a name="members"></a>成员  
 DBGPROP_INFO_NAME  
 初始化`bstrName`字段。  
  
 DBGPROP_INFO_TYPE  
 初始化`bstrType`字段。  
  
 DBGPROP_INFO_VALUE  
 初始化`bstrValue`字段。  
  
 DBGPROP_INFO_FULLNAME  
 初始化`bstrFullName`字段。  
  
 DBGPROP_INFO_ATTRIBUTES  
 初始化`dwAttrib`字段。  
  
 DBGPROP_INFO_DEBUGPROP  
 初始化`pDebugProp`字段包含`IDebugProperty`接口。  
  
 DBGPROP_INFO_AUTOEXPAND  
 指定的值字段应包含自动扩展值中，是否可用，此类型的对象。  
  
## <a name="see-also"></a>请参阅  
 [DebugPropertyInfo 结构](../../winscript/reference/debugpropertyinfo-structure.md)   
 [IDebugProperty 接口](../../winscript/reference/idebugproperty-interface.md)