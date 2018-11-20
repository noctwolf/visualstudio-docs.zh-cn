---
title: IEnumDebugAddresses::GetCount |Microsoft Docs
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
- IEnumDebugAddresses::GetCount
helpviewer_keywords:
- IEnumDebugAddresses::GetCount method
ms.assetid: f2ca8ff8-539f-457c-83f8-9bbf97618065
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1b9ce150eac3137c9fd078fd111b83a517f1b825
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51729916"
---
# <a name="ienumdebugaddressesgetcount"></a>IEnumDebugAddresses::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此方法返回的枚举中的元素数。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetCount(  
   [out] ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pcelt`  
 [out]枚举中返回元素的数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法不是惯用的 COM 枚举接口指定的下一步、 克隆、 跳过和重置需要实现的一部分。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)

