---
title: IDebugPortSupplier2::GetPortSupplierName |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2::GetPortSupplierName
helpviewer_keywords:
- IDebugPortSupplier2::GetPortSupplierName
ms.assetid: e4c368ab-640d-4b5b-9f74-810dc9364d8f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a19ba4c4524d576b50260ef15f1f5889c29f05fe
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49876095"
---
# <a name="idebugportsupplier2getportsuppliername"></a>IDebugPortSupplier2::GetPortSupplierName
获取端口供应商名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetPortSupplierName(   
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetPortSupplierName(   
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrName`  
 [out]返回端口供应商的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)