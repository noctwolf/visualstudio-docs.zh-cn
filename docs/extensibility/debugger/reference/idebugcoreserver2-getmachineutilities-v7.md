---
title: IDebugCoreServer2::GetMachineUtilities_V7 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 96f374d83af705d8e9376d8767c822af82ed4d4a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
此方法获取服务器的计算机实用程序。  
  
> [!NOTE]
>  此方法已过时： 不要使用 ([!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]始终返回`E_NOTIMPL`如果调用此方法)。 出于历史原因保留它。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMachineUtilities_V7(  
   IDebugMDMUtil2_V7** ppUtil  
);  
```  
  
```csharp  
int GetMachineUtilities_V7(  
   out IDebugMDMUtil2_V7 ppUtil  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppUtil`  
 [out]返回`IDebugMDMUtil2_V7`表示机实用程序信息的接口。  
  
## <a name="return-value"></a>返回值  
 始终返回`E_NOTIMPL`，指示未实现方法。  
  
## <a name="remarks"></a>备注  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 始终返回`E_NOTIMPL`如果调用此方法。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)