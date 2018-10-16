---
title: IDebugDocumentPosition2::IsPositionInDocument |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugDocumentPosition2::IsPositionInDocument
helpviewer_keywords:
- IDebugDocumentPosition2::IsPositionInDocument
ms.assetid: d5cf57cb-b93b-4e1d-bec9-185f4fe8668d
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9d16874ef7f63c0b9539691760bebb0edaf83643
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49176379"
---
# <a name="idebugdocumentposition2ispositionindocument"></a>IDebugDocumentPosition2::IsPositionInDocument
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

确定给定文档中是否包含文档位置。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT IsPositionInDocument(   
   IDebugDocument2* pDoc  
);  
```  
  
```csharp  
int IsPositionInDocument(   
   IDebugDocument2 pDoc  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pDoc`  
 [in][IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)对象，表示包含文档候选项。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法主要用于在中设置断点[IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)接口。 加载文档，被调用的断点位置，以确定文档是否包含此位置。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)   
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)

