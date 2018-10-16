---
title: IEnumDebugObjects::Reset |Microsoft Docs
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
- IEnumDebugObjects::Reset
helpviewer_keywords:
- IEnumDebugObjects::Reset method
ms.assetid: 4a245e47-cc39-4177-b83d-083ea0e3190f
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5630232228dbd5171eae86e88f2cb1324c862b4e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49276754"
---
# <a name="ienumdebugobjectsreset"></a>IEnumDebugObjects::Reset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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
 调用此方法下, 一步调用后[下一步](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)返回枚举的第一个元素。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)   
 [下一篇](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)

