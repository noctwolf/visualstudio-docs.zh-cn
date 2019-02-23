---
title: IDebugClassField::GetEnclosingClass |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::GetEnclosingClass
helpviewer_keywords:
- IDebugClassField::GetEnclosingClass method
ms.assetid: a0c12e3c-9ea0-4dfb-9e45-8cea18725022
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9e6b2cfae694d0d95f70b2251efc66764df1b539
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56682006"
---
# <a name="idebugclassfieldgetenclosingclass"></a>IDebugClassField::GetEnclosingClass
获取包含此类的类。

## <a name="syntax"></a>语法

```cpp
HRESULT GetEnclosingClass(
    IDebugClassField** ppClassField
);
```

```csharp
int GetEnclosingClass(
    out IDebugClassField ppClassField
);
```

#### <a name="parameters"></a>参数
`ppClassField`

 [out]返回[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)对象表示封闭类。 如果没有封闭类，则返回 null 值。

## <a name="return-value"></a>返回值
如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
如果类由此[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)对象是一个嵌套的类，则`ppClassField`参数返回`IDebugClassField`对象表示封闭类。 例如，给定此类定义：

```
class RootClass {
    class NestedClass { }
};
```

调用`GetEnclosingClass`方法`IDebugClassField`对象，表示`NestedClass`类返回`IDebugClassField`对象，表示该类`RootClass`。

## <a name="see-also"></a>请参阅
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
