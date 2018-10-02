---
title: IEnumDebugFields::Reset |Microsoft Docs
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
- IEnumDebugFields::Reset
helpviewer_keywords:
- IEnumDebugFields::Reset method
ms.assetid: 38ff61e4-0120-42e8-971a-16be6050b425
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fab8459f1cb279fd514730e7c3319bba951d04a6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471941"
---
# <a name="ienumdebugfieldsreset"></a>IEnumDebugFields::Reset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IEnumDebugFields::Reset](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugfields-reset)。  
  
此方法将枚举重置为第一个元素。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Reset(void);  
```  
  
```csharp  
int Reset();  
```  
  
#### <a name="parameters"></a>参数  
 无  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法下, 一步调用后[下一步](../../../extensibility/debugger/reference/ienumdebugfields-next.md)返回枚举的第一个元素。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [下一篇](../../../extensibility/debugger/reference/ienumdebugfields-next.md)

