---
title: IDebugDocument2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocument2
helpviewer_keywords:
- IDebugDocument2 interface
ms.assetid: 1bc58426-dbf5-4471-9aad-9d66cd80eef0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 36ac127e6cd6e25fd42c4859e723c883ecaffa82
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109150"
---
# <a name="idebugdocument2"></a>IDebugDocument2
此接口表示源文档。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugDocument2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 通常实现此接口。 它需要提供的源代码和磁盘上不存在源时，调试引擎 (DE) 还可以实现此接口。  在这种情况下，DE 还会实施[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)和[IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)接口，以及某些其他方法[IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)和[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)接口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 上的方法`IDebugDocumentContext2`， `IDebugDisassemblyStream2`， `IDebugDocumentPosition2`，和`IDebugActivateDocumentEvent2`接口都返回此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugDocument2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)|获取文档的名称中有几种形式之一。|  
|[GetDocumentClassID](../../../extensibility/debugger/reference/idebugdocument2-getdocumentclassid.md)|获取文档的类标识符。|  
  
## <a name="remarks"></a>备注  
 仅当 DE 提供的源代码时，被实现此接口。 例如，当正在调试 HTML 页上的脚本，DE 提供的源代码因为下载的源或将其动态生成，并且不存在为磁盘文件。 当调试传统的语言，例如 c + +，此接口不需要实现。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)   
 [GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)