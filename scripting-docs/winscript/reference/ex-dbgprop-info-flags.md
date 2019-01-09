---
title: EX_DBGPROP_INFO_FLAGS |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- EX_DBGPROP_INFO_FLAGS
apilocation:
- scrobj.dll
helpviewer_keywords:
- EX_DBGPROP_INFO_FLAGS
ms.assetid: ee309dfe-9432-4dff-8756-7a8d677f9dcc
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b40ef5c0ceb950873b47033d51555c3ba2fe27a
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094505"
---
# <a name="exdbgpropinfoflags"></a>EX_DBGPROP_INFO_FLAGS
用于指定`ExtendedDebugPropertyInfo`字段。  
  
## <a name="syntax"></a>语法  
  
```cpp
enum {  
   EX_DBGPROP_INFO_ID  =0x0100,  
   EX_DBGPROP_INFO_NTYPE  =0x0200,  
   EX_DBGPROP_INFO_NVALUE  =0x0400,  
   EX_DBGPROP_INFO_LOCKBYTES  =0x0800,  
   EX_DBGPROP_INFO_DEBUGEXTPROP  =0x1000  
};  
```  
  
## <a name="members"></a>成员  
 EX_DBGPROP_INFO_ID  
 初始化的属性标识符。  
  
 EX_DBGPROP_INFO_NTYPE  
 初始化类型的属性。  
  
 EX_DBGPROP_INFO_NVALUE  
 初始化属性的值。  
  
 EX_DBGPROP_INFO_LOCKBYTES  
 初始化`plb`字段。  
  
 EX_DBGPROP_INFO_DEBUGEXTPROP  
 初始化`pDebugExtProp`字段包含`IDebugExtendedProperty`接口。  
  
## <a name="see-also"></a>请参阅  
 [ExtendedDebugPropertyInfo 结构](../../winscript/reference/extendeddebugpropertyinfo-structure.md)   
 [IDebugExtendedProperty 接口](../../winscript/reference/idebugextendedproperty-interface.md)