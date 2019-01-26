---
title: IDebugTypeFieldBuilder | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugTypeFieldBuilder interface
ms.assetid: 2dfed0be-6972-4bec-baec-f0b78df9ef97
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a1364584dfe56d6b9d009bff6b407060a4fc85fa
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54972948"
---
# <a name="idebugtypefieldbuilder"></a>IDebugTypeFieldBuilder
表示创建表示一种类型的字段的功能。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugTypeFieldBuilder : IUnknown  
```  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口是从符号提供程序获取的。  
  
## <a name="methods"></a>方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[CreatePrimitive](../../../extensibility/debugger/reference/idebugtypefieldbuilder-createprimitive.md)|创建表示基元类型的对象。|  
|[CreatePointerToType](../../../extensibility/debugger/reference/idebugtypefieldbuilder-createpointertotype.md)|创建为指定类型的指针。|  
  
## <a name="requirements"></a>要求  
 标头：Sh.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll