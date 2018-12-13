---
title: IDebugPortPicker::SetSite |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugPortPicker::SetSite
ms.assetid: 7319e187-adfe-4b3f-aec9-521356fb5a8a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 00730a5338a3355f2397a91bc7a3693b30dca31b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49930604"
---
# <a name="idebugportpickersetsite"></a>IDebugPortPicker::SetSite
设置服务提供程序。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetSite(  
   IServiceProvider * pSP  
);  
```  
  
```csharp  
public int SetSite(  
   IServiceProvider pSP  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pSP`  
 [in]对服务提供程序的接口的引用。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 在调用任何其他方法之前，将调用此方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)