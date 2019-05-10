---
title: IDebugReference2::SetValueAsReference | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::SetValueAsReference
helpviewer_keywords:
- IDebugReference2::SetValueAsReference
ms.assetid: 94a545d2-16b9-45e9-b2e7-4e49ff90aad0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0fc6e2fee354d6dcc76676bf02d4ed88e1799f26
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458648"
---
# <a name="idebugreference2setvalueasreference"></a>IDebugReference2::SetValueAsReference
设置引用的另一个引用值。 留待将来使用。

## <a name="syntax"></a>语法

```cpp
HRESULT SetValueAsReference ( 
   IDebugReference2** rgpArgs,
   DWORD              dwArgCount,
   IDebugReference2*  pValue,
   DWORD              dwTimeout
);
```

```cpp
int SetValueAsReference ( 
   IDebugReference2[] rgpArgs,
   uint               dwArgCount,
   IDebugReference2   pValue,
   uint               dwTimeout
);
```

## <a name="parameters"></a>参数
 `rgpArgs`\

 [in]一个数组[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)对象用于确定如何设置引用值。

 `dwArgCount`\

 [in]数组中引用的数目。

 `pValue`\

 [in][IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)对象从其设置属性值。

 `dwTimeout`\

 [in]最大时间 （毫秒），此方法返回前等待。 使用`INFINITE`无限期等待。

## <a name="return-value"></a>返回值
 始终返回 `E_NOTIMPL`。

## <a name="see-also"></a>请参阅
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)