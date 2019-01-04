---
title: IDebugDefaultPort2::GetServer |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDefaultPort2::GetServer
helpviewer_keywords:
- IDebugDefaultPort2::GetServer
ms.assetid: cacb4b74-0f39-471c-af38-54b73f5b2868
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 975c86e0f7674d91b16073c2627414ae1de04081
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53841828"
---
# <a name="idebugdefaultport2getserver"></a>IDebugDefaultPort2::GetServer
此方法获取此端口的服务器的接口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetServer(  
   IDebugCoreServer3** ppServer  
);  
```  
  
```csharp  
int GetServer(  
   out IDebugCoreServer3 ppServer  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppServer`  
 [out]返回一个对象，实现[IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)实现由 Visual Studio 和表示该端口位于的服务器。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)