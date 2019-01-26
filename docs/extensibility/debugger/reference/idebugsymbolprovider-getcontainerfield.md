---
title: IDebugSymbolProvider::GetContainerField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugSymbolProvider::GetContainerField
helpviewer_keywords:
- IDebugSymbolProvider::GetContainerField method
ms.assetid: d6b56b4f-a96b-4fa7-87c1-bac4e58fa766
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1cced3eb3bea16d3c45fba69f86f607b8332f679
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935067"
---
# <a name="idebugsymbolprovidergetcontainerfield"></a>IDebugSymbolProvider::GetContainerField
此方法获取包含调试地址的字段。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetContainerField(   
   IDebugAddress*         pAddress,  
   IDebugContainerField** ppContainerField  
);  
```  
  
```csharp  
int GetContainerField(  
   IDebugAddress            pAddress,   
   out IDebugContainerField ppContainerField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAddress`  
 [in]地址由[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口。  
  
 `ppContainerField`  
 [out]返回表示容器字段[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)