---
title: IDebugActivateDocumentEvent2::GetDocument |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugActivateDocumentEvent2::GetDocument
helpviewer_keywords:
- GetDocument method
- IDebugActivateDocumentEvent2::GetDocument method
ms.assetid: b3c32f1b-f3de-409d-920d-ba7b3fa84fcd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ef8059279785991d363ec3be4a870cefcab4c0b8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53908965"
---
# <a name="idebugactivatedocumentevent2getdocument"></a>IDebugActivateDocumentEvent2::GetDocument
获取要激活的文档。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetDocument (   
   IDebugDocument2** ppDoc  
);  
```  
  
```csharp  
int GetDocument (   
   out IDebugDocument2 ppDoc  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppDoc`  
 [out]返回[IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)对象，表示要激活的文档。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)   
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)