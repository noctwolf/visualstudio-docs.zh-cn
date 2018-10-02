---
title: IDebugCoreServer2::GetMachineUtilities_V7 |Microsoft Docs
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
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 217118d96fbcf50f267570bcd1c26abd5d8128c3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471731"
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugCoreServer2::GetMachineUtilities_V7](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcoreserver2-getmachineutilities-v7)。  
  
此方法获取服务器的计算机实用程序。  
  
> [!NOTE]
>  此方法已过时： 不要使用 ([!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]始终返回`E_NOTIMPL`如果调用此方法)。 保留历史原因。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 始终返回`E_NOTIMPL`如果调用此方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)

