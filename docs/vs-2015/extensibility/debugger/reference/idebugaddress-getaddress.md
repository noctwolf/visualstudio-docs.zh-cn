---
title: IDebugAddress::GetAddress |Microsoft Docs
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
- IDebugAddress::GetAddress
helpviewer_keywords:
- IDebugAddress:GetAddress method
ms.assetid: 2590387b-5d36-4116-9a75-737957b8898e
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ddb3b6e3d8055dd9a5b6304cf57a355986706b0d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49186753"
---
# <a name="idebugaddressgetaddress"></a>IDebugAddress::GetAddress
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

返回描述对象并将其作用域或容器内的其位置的结构。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetAddress (  
   DEBUG_ADDRESS * pAddress  
);  
```  
  
```csharp  
int GetAddress(  
   DEBUG_ADDRESS[] pAddress  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAddress`  
 [in、 out]一个[DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)通过此方法来填充的结构。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)结构传递给此方法，然后使用相应的信息对其进行填充。 如何解释此信息取决于返回的信息和符号处理程序本身的类型。 请参阅[DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)的更多详细信息。  
  
## <a name="see-also"></a>请参阅  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)

