---
title: "IEnumDebugCodeContexts2 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugCodeContexts2
helpviewer_keywords: IEnumDebugCodeContexts2
ms.assetid: 72915146-215f-4c99-a034-131b2b474e0e
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: cd6ead902a65a9f3e5e392b1b9dbeed135f326b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugcodecontexts2"></a>IEnumDebugCodeContexts2
此接口枚举关联与调试会话中，或与特定的程序或文档的代码上下文。  
  
## <a name="syntax"></a>语法  
  
```  
IEnumDebugCodeContexts2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 调试引擎 (DE) 实现此接口可表示的代码在程序中的特定文本位置的上下文列表或特定文档上下文的代码上下文的列表。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)以获取此接口，表示代码上下文的程序的源文档中的特定文本位置的列表。  
  
 调用[EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)以获取此接口，表示特定的源文档中的所有代码上下文的列表。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IEnumDebugCodeContexts2`。  
  
|方法|描述|  
|------------|-----------------|  
|[下一篇](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)|检索指定的数目的枚举序列中的代码上下文。|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-skip.md)|跳过指定的数目的枚举序列中的代码上下文。|  
|[重置](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-reset.md)|将枚举序列重置到开头。|  
|[克隆](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-clone.md)|创建包含与当前的枚举器相同的枚举状态的枚举。|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-getcount.md)|获取枚举器中的代码上下文的数量。|  
  
## <a name="remarks"></a>备注  
 Visual Studio 调用[EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)以填充列表的代码上下文用户可以选择从时设置的下一个语句或显示源文件反汇编。 例如，当存在多个实例的 c + + 样式模板时，可以发生多个代码上下文。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)