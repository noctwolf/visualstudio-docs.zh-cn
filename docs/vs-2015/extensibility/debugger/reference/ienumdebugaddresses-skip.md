---
title: IEnumDebugAddresses::Skip |Microsoft Docs
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
- IEnumDebugAddresses::Skip
helpviewer_keywords:
- IEnumDebugAddresses::Skip method
ms.assetid: ed9a8e71-30ef-414b-9da5-c9a2a251b84e
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8b19f51222dafb95c12c6105a4f6dd22befa24d8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470027"
---
# <a name="ienumdebugaddressesskip"></a>IEnumDebugAddresses::Skip
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IEnumDebugAddresses::Skip](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugaddresses-skip)。  
  
此方法跳过指定数量的元素。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Skip(  
   [in] ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]要跳过的元素数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果`celt`大于剩余的元素数; 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果`celt`指定的值数比大剩余元素的枚举设置为结束和`S_FALSE`返回。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)

