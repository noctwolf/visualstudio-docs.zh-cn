---
title: IDebugProperty2::SetValueAsString |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::SetValueAsString
helpviewer_keywords:
- IDebugProperty2::SetValueAsString
ms.assetid: 9e6a5054-41b7-4223-b509-b93689d366a5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6acc3c0c0ec271793832783b2fb7eb9f2ff2309a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686478"
---
# <a name="idebugproperty2setvalueasstring"></a>IDebugProperty2::SetValueAsString
从给定字符串中设置属性的值。

## <a name="syntax"></a>语法

```cpp
HRESULT SetValueAsString ( 
   LPCOLESTR pszValue,
   UINT      nRadix,
   DWORD     dwTimeout
);
```

```csharp
int SetValueAsString ( 
   string pszValue,
   uint   nRadix,
   uint   dwTimeout
);
```

#### <a name="parameters"></a>参数
 `pszValue`

 [in]包含要设置的值的字符串。

 `nRadix`

 [in]用于解释任何数字信息的基数。 这可以是 0，以尝试自动确定基数。

 `dwTimeout`

 [in]指定以毫秒为单位，此方法返回前等待的最长时间。 使用`INFINITE`无限期等待。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则返回错误代码。 下表显示了其他可能的值。

|值|描述|
|-----------|-----------------|
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|字符串可以转换为属性值，或无法设置属性值。|
|`E_SETVALUE_VALUE_IS_READONLY`|该属性是只读的。|

## <a name="see-also"></a>请参阅
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)