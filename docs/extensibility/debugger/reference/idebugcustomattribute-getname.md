---
title: IDebugCustomAttribute::GetName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttribute::GetName
helpviewer_keywords:
- IDebugCustomAttribute::GetName
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2556a424e5109e75b667e9f32ecac5cc26ca781b
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66205339"
---
# <a name="idebugcustomattributegetname"></a>IDebugCustomAttribute::GetName
获取自定义特性的名称。

## <a name="syntax"></a>语法

```cpp
HRESULT GetName( 
   BSTR* bstrName
);
```

```csharp
int GetName(
   out string bstrName
);
```

## <a name="parameters"></a>参数
`bstrName`\
[out]返回包含自定义特性的名称的字符串。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 此方法返回的命名对应于用于声明属性的类的名称。 这可能不完全对应于自定义特性类本身的名称，如 C# 允许在声明中使用时要删除自定义属性名称从"Attribute"后缀。

## <a name="see-also"></a>请参阅
- [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)