---
title: IDebugCoreServer3::QueryIsLocal | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3::QueryIsLocal
helpviewer_keywords:
- IDebugCoreServer3::QueryIsLocal
ms.assetid: cca030de-f853-4ed7-b2fb-395f08a6b884
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fd516411ddc032942a189b5b39b4bc152e3d92c8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54976870"
---
# <a name="idebugcoreserver3queryislocal"></a>IDebugCoreServer3::QueryIsLocal
确定服务器是否本地给调用方。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```csharp  
int QueryIsLocal();  
```  
  
## <a name="return-value"></a>返回值  
 返回`S_OK`以指示服务器是本地。 返回`S_FALSE`如果服务器运行 msvsmon.exe，通常用于远程调试的实例中。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)