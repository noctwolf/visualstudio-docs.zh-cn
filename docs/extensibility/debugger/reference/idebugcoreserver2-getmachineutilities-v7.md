---
title: IDebugCoreServer2::GetMachineUtilities_V7 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9b7b0aa54cb5102867ba536729404ad298db9fd3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56678171"
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
此方法获取服务器的计算机实用程序。

> [!NOTE]
>  此方法已过时： 不要使用 ([!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]始终返回`E_NOTIMPL`如果调用此方法)。 保留历史原因。

## <a name="syntax"></a>语法

```cpp
HRESULT GetMachineUtilities_V7(
   IDebugMDMUtil2_V7** ppUtil
);
```

```csharp
int GetMachineUtilities_V7(
   out IDebugMDMUtil2_V7 ppUtil
);
```

#### <a name="parameters"></a>参数
 `ppUtil`

 [out]返回`IDebugMDMUtil2_V7`表示机实用程序信息的接口。

## <a name="return-value"></a>返回值
 始终返回`E_NOTIMPL`，指示未实现方法。

## <a name="remarks"></a>备注
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 始终返回`E_NOTIMPL`如果调用此方法。

## <a name="see-also"></a>请参阅
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)