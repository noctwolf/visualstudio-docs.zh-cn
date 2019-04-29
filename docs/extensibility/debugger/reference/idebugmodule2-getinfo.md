---
title: IDebugModule2::GetInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugModule2::GetInfo
helpviewer_keywords:
- GetInfo method
- IDebugModule2::GetInfo method
ms.assetid: de337e66-294f-4ac9-b21e-71fac7418e36
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a0a5ad3d7651e89c2ef864a184155e8b0a430d79
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62872726"
---
# <a name="idebugmodule2getinfo"></a>IDebugModule2::GetInfo
获取有关此模块的信息。

## <a name="syntax"></a>语法

```cpp
HRESULT GetInfo( 
   MODULE_INFO_FIELDS dwFields,
   MODULE_INFO*       pInfo
);
```

```cpp
int GetInfo( 
   enum_MODULE_INFO_FIELDS dwFields,
   MODULE_INFO[]           pInfo
);
```

#### <a name="parameters"></a>参数
 `dwFields`

 [in]中的标志的组合[MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)枚举，用于指定的哪些字段`pInfo`要填写。

 `pInfo`

 [in、 out]一个[MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)使用模块的说明填充的结构。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)结构中包含的模块中显示的名称**模块**窗口。

## <a name="see-also"></a>请参阅
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)