---
title: IDebugPort2::GetPortRequest |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPort2::GetPortRequest
helpviewer_keywords:
- IDebugPort2::GetPortRequest
ms.assetid: 14abf847-0675-4fa8-872e-971e00c84224
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 433f9724a712620e86cb78ab64e1ce27e6151d30
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49920100"
---
# <a name="idebugport2getportrequest"></a>IDebugPort2::GetPortRequest
获取以前用来创建 （如果可用） 的端口的端口的说明。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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