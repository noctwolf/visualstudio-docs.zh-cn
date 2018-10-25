---
title: IDebugDocumentContext2::Seek |Microsoft Docs
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
- IDebugDocumentContext2::Seek
helpviewer_keywords:
- IDebugDocumentContext2::Seek
ms.assetid: 71501356-8a82-4d36-b354-6625bdd2baa0
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 857a83b975d2042eebcb4e31e82976efa6072207
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49929148"
---
# <a name="idebugdocumentcontext2seek"></a>IDebugDocumentContext2::Seek
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

按给定数量的语句或行移动文档上下文。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Seek(   
   int                      nCount,  
   IDebugDocumentContext2** ppDocContext  
);  
```  
  
```cpp#  
int Seek(   
   int                        nCount,  
   out IDebugDocumentContext2 ppDocContext  
);  
```  
  
#### <a name="parameters"></a>参数  
 `nCount`  
 [in]语句或继续推行，具体取决于文档上下文的行数。  
  
 `ppDocContext`  
 [out]返回一个新[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)对象的新位置。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)

