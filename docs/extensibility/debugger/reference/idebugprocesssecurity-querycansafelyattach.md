---
title: IDebugProcessSecurity::QueryCanSafelyAttach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7cbce46afaa6227f5d15720be8aebd4c60f5f236
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55015493"
---
# <a name="idebugprocesssecurityquerycansafelyattach"></a>IDebugProcessSecurity::QueryCanSafelyAttach
此方法允许端口提供程序，用户将附加到不安全的过程之前显示一条警告。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT QueryCanSafelyAttach();  
```  
  
```csharp  
int QueryCanSafelyAttach();  
```  
  
## <a name="return-value"></a>返回值  
 返回值如下所示：  
  
-   `S_OK`：是安全的附加到进程，并且会显示任何警告对话框。  
  
-   `S_FALSE`：附加可能是一个安全问题，并且会显示一个警告对话框。  
  
-   `FAILURE`：附加到进程将失败。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)