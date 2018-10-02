---
title: IDebugProcessSecurity::QueryCanSafelyAttach |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProcessSecurity::QueryCanSafelyAttach
ms.assetid: 63ec1ae8-27da-4574-aa15-1c986fe9fe58
caps.latest.revision: 5
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 243c8556e38bd89200ca591d4b087e441baf57f1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484180"
---
# <a name="idebugprocesssecurityquerycansafelyattach"></a>IDebugProcessSecurity::QueryCanSafelyAttach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProcessSecurity::QueryCanSafelyAttach](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocesssecurity-querycansafelyattach)。  
  
此方法允许端口提供程序，用户将附加到不安全的过程之前显示一条警告。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT QueryCanSafelyAttach();  
```  
  
```csharp  
int QueryCanSafelyAttach();  
```  
  
## <a name="return-value"></a>返回值  
 返回值如下所示：  
  
-   `S_OK`： 是安全的附加到进程，并且会显示任何警告对话框。  
  
-   `S_FALSE`： 附加可能是一个安全问题，并且会显示一个警告对话框。  
  
-   `FAILURE`： 附加到进程将失败。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)

