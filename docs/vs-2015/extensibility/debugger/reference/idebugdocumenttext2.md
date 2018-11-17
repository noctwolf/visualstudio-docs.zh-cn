---
title: IDebugDocumentText2 |Microsoft Docs
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
- IDebugDocumentText2
helpviewer_keywords:
- IDebugDocumentText2 interface
ms.assetid: e85f50a3-211c-4220-a9f4-789950ba2782
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 85b5d9e78af9e4e49b3a985ca00ffad102e6b53d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51728849"
---
# <a name="idebugdocumenttext2"></a>IDebugDocumentText2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此接口表示文本文档。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugDocumentText2 : IDebugDocument2  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 调试引擎 (DE) 实现此接口时需要提供的源代码是以文本形式。 由于这是最典型的情况下，如果实现了 DE [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)接口，它还应实现`IDebugDocumentText2`接口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 使用`QueryInterface`方法来获取此接口从`IDebugDocument2`接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 除了上的方法`IDebugDocument2`接口，此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetSize](../../../extensibility/debugger/reference/idebugdocumenttext2-getsize.md)|检索在此位置上的文档中的文本的大小。|  
|[GetText](../../../extensibility/debugger/reference/idebugdocumenttext2-gettext.md)|从文档中的指定位置检索的文本。|  
  
## <a name="remarks"></a>备注  
 实现此接口的对象，还必须实现<xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer>接口，提供<xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint>接口[IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)对象。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)

