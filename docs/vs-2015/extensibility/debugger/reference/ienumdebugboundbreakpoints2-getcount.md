---
title: IEnumDebugBoundBreakpoints2::GetCount |Microsoft Docs
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
- IEnumDebugBoundBreakpoints2::GetCount
helpviewer_keywords:
- IEnumDebugBoundBreakpoints2::GetCount
ms.assetid: 5a572eeb-beb7-4fc7-8259-792d277069be
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4cd9bc889fedc11b755807a8fa79670f669e67ab
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49918644"
---
# <a name="ienumdebugboundbreakpoints2getcount"></a>IEnumDebugBoundBreakpoints2::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

枚举中返回元素的数。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetCount(  
   ULONG* pcelt  
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
 此方法不是惯用的 COM 枚举接口，只有指定的一部分`Next`， `Clone`， `Skip`，和`Reset`方法需要实现。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)

