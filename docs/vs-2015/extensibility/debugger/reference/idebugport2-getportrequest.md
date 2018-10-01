---
title: IDebugPort2::GetPortRequest |Microsoft Docs
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
- IDebugPort2::GetPortRequest
helpviewer_keywords:
- IDebugPort2::GetPortRequest
ms.assetid: 14abf847-0675-4fa8-872e-971e00c84224
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9570f1b7e1e77483d0cff001ce09a4b583416e1f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481883"
---
# <a name="idebugport2getportrequest"></a>IDebugPort2::GetPortRequest
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugPort2::GetPortRequest](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugport2-getportrequest)。  
  
获取以前用来创建 （如果可用） 的端口的端口的说明。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetPortRequest(   
   IDebugPortRequest2** ppRequest  
);  
```  
  
```csharp  
int GetPortRequest(   
   out IDebugPortRequest2 ppRequest  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppRequest`  
 [out]返回[IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)对象，表示用于创建该端口的请求。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  返回`E_PORT_NO_REQUEST`如果端口不使用创建[IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)端口请求。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)

