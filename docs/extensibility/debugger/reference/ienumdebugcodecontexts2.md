---
title: IEnumDebugCodeContexts2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugCodeContexts2
helpviewer_keywords:
- IEnumDebugCodeContexts2
ms.assetid: 72915146-215f-4c99-a034-131b2b474e0e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc6ff9a173bcfbb87606fe493697857d7ec2b323
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122556"
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
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)