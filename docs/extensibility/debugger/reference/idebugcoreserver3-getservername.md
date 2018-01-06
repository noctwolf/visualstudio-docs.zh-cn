---
title: "IDebugCoreServer3::GetServerName |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer3::GetServerName
helpviewer_keywords: IDebugCoreServer3::GetServerName
ms.assetid: 0fc3fcf5-d6a3-4a00-bf14-458b8645714e
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: db861afe67050ba0ce84277941653d91b13dd769
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver3getservername"></a>IDebugCoreServer3::GetServerName
检索服务器的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetServerName(  
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetServerName(  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrName`  
 [out]返回服务器的名称。  
  
> [!NOTE]
>  调用方负责释放字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 输入友好的服务器名称，调用[GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)