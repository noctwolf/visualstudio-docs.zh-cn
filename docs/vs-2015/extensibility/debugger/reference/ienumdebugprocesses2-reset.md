---
title: IEnumDebugProcesses2::Reset | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2::Reset
helpviewer_keywords:
- IEnumDebugProcesses2::Reset
ms.assetid: 31cbde4f-0bba-497a-9969-d2c342ef4a7b
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 450b469073e90b497cf2bd77e2862e48cad81b6d
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58926104"
---
# <a name="ienumdebugprocesses2reset"></a>IEnumDebugProcesses2::Reset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

将枚举重置为第一个元素。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法下, 一步调用后[下一步](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)方法返回的第一个元素的枚举。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)
