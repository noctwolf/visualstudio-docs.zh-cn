---
title: TEXT_POSITION |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- TEXT_POSITION
helpviewer_keywords:
- TEXT_POSITION structure
ms.assetid: 6dcec574-a852-49fa-8c2e-2e71cbb5e3c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 09f77fa2f79f6e2e60a4a1b29e3c1a85e791c75b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49910715"
---
# <a name="textposition"></a>TEXT_POSITION
描述在给定的文本中的行和列位置。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _tagTEXT_POSITION {   
   DWORD dwLine;  
   DWORD dwColumn;  
} TEXT_POSITION;  
```  
  
```csharp  
public struct TEXT_POSITION {   
   public uint dwLine;  
   public uint dwColumn;  
};  
```  
  
## <a name="members"></a>成员  
 dwLine  
 源文件中的行的索引。  
  
 dwColumn  
 行中的字符偏移量。  
  
## <a name="remarks"></a>备注  
 在使用此结构[CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)并[DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)结构。  
  
 通过以下方法调用填充此结构：  
  
- [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)  
  
- [GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)  
  
- [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)  
  
- [GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)  
  
  此结构作为参数传递给以下方法：  
  
- [GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)  
  
- [onInsertText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-oninserttext.md)  
  
- [onRemoveText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onremovetext.md)  
  
- [onReplaceText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onreplacetext.md)  
  
- [onUpdateTextAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatetextattributes.md)  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)   
 [GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)   
 [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)   
 [GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)   
 [GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)   
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)