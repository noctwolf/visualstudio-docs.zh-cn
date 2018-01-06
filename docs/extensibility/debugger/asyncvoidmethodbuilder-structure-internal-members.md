---
title: "AsyncVoidMethodBuilder 结构的内部成员 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, AsyncVoidMethodBuilder structure [.NET Framework]
- AsyncVoidMethodBuilder structure [.NET Framework debug engines]
ms.assetid: fe2970ab-d4c5-4355-a8e4-772ee0a57178
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2debb60ed63a68f3925ed91ee6b8d374b84ce392
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="asyncvoidmethodbuilder-structure---internal-members"></a>AsyncVoidMethodBuilder 结构的内部成员
本主题介绍的内部成员<xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>类。 有关此类的常规信息，请参阅<xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>参考主题。  
  
 **命名空间：** <xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 **程序集：** mscorlib （mscorlib.dll) 中  
  
 由于无法访问这些内部成员在.NET Framework 中，以下语法提供共同点中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```  
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncVoidMethodBuilder  
       extends System.ValueType  
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder  
```  
  
## <a name="internal-members"></a>内部成员  
  
|name|描述|  
|----------|-----------------|  
|[ObjectIdForDebugger 属性](../../extensibility/debugger/asyncvoidmethodbuilder-objectidfordebugger-property.md)|获取可用于唯一标识调试器到此生成器的对象。|  
|[m_objectIdForDebugger 字段](../../extensibility/debugger/asyncvoidmethodbuilder-m-objectidfordebugger-field.md)|表示调试器用于唯一标识此生成器的延迟初始化的对象。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>   
 [.NET Framework 的并行扩展内幕](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)