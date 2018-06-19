---
title: IDebugDocumentPositionOffset2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugDocumentPositionOffset2 interface
ms.assetid: f1b05db3-50d8-453f-a72f-e68b239236a4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f08b278d75068351d6d65511f74209c7208024cf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31106872"
---
# <a name="idebugdocumentpositionoffset2"></a>IDebugDocumentPositionOffset2
表示为字符偏移量在源文件中的位置。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugDocumentPositionOffset2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 由 IDE 实现和使用的调试引擎。  
  
## <a name="methods"></a>方法  
 下表显示的方法`IDebugDocumentPositionOffset2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2-getrange.md)|检索当前的文档位置的范围。|  
  
## <a name="remarks"></a>备注  
 这将返回相同的信息[GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)但在`char`从文档的开头偏移量。 像它将存在于磁盘，即字符，而不是通常返回的行和列信息的一维数组，这会带来文档。  
  
## <a name="requirements"></a>要求  
 标头： Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)