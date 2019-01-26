---
title: AsyncVoidMethodBuilder 结构-内部成员 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, AsyncVoidMethodBuilder structure [.NET Framework]
- AsyncVoidMethodBuilder structure [.NET Framework debug engines]
ms.assetid: fe2970ab-d4c5-4355-a8e4-772ee0a57178
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7fa4eb73257b98a588102bee96c037e2d302e96c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54976649"
---
# <a name="asyncvoidmethodbuilder-structure---internal-members"></a>AsyncVoidMethodBuilder 结构-内部成员
本主题介绍的内部成员的<xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>类。 有关此类的常规信息，请参阅<xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>参考主题。  
  
 **Namespace**：<xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 **程序集：** mscorlib （在 mscorlib.dll 中)  
  
 无法从.NET Framework 来访问这些内部成员，因为以下语法提供通用中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```csharp  
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncVoidMethodBuilder  
       extends System.ValueType  
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder  
```  
  
## <a name="internal-members"></a>内部成员  
  
|name|描述|  
|----------|-----------------|  
|[ObjectIdForDebugger 属性](../../extensibility/debugger/asyncvoidmethodbuilder-objectidfordebugger-property.md)|获取可用于唯一地标识调试器到此生成器的对象。|  
|[m_objectIdForDebugger 字段](../../extensibility/debugger/asyncvoidmethodbuilder-m-objectidfordebugger-field.md)|表示调试器用于唯一标识此生成器的延迟初始化的对象。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>   
 [.NET Framework 的并行扩展内幕](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)