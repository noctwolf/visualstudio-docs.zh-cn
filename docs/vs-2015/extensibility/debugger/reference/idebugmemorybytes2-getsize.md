---
title: IDebugMemoryBytes2::GetSize |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMemoryBytes2::GetSize
helpviewer_keywords:
- IDebugMemoryBytes2::GetSize method
- GetSize method
ms.assetid: dae64c5f-5b54-40c3-b32f-ec3b16c093f7
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7b5ad9b734de92f6c3b615acb8480f324ed5f5f8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483519"
---
# <a name="idebugmemorybytes2getsize"></a>IDebugMemoryBytes2::GetSize
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugMemoryBytes2::GetSize](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorybytes2-getsize)。  
  
检索大小 （字节） 的内存由此[IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)对象。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetSize(   
   UINT64* pqwSize  
);  
```  
  
```csharp  
int GetSize(  
   out ulong pqwSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pqwSize`  
 [out]返回的大小，以字节为单位的内存空间。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)

