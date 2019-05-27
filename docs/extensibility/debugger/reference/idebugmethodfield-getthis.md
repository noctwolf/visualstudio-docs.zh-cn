---
title: IDebugMethodField::GetThis |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::GetThis
helpviewer_keywords:
- IDebugMethodField::GetThis method
ms.assetid: cc235bea-e909-4d8c-ab54-936736c803fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a3e88f209b506d8baf10a779d282a78122c274fb
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211927"
---
# <a name="idebugmethodfieldgetthis"></a>IDebugMethodField::GetThis
获取`this`(`Me`中[!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]) 包含方法的对象的指针。

## <a name="syntax"></a>语法

```cpp
HRESULT GetThis( 
   IDebugClassField** ppClass
);
```

```csharp
int GetThis(
   out IDebugClassField ppClass
);
```

## <a name="parameters"></a>参数
`ppClass`\
[out]返回[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)对象，表示"this"指针。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 在面向对象的语言，通常不存在类的当前实例化的隐式的指针。 这称为`this`在C#/C++和 as`Me`中[!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]。

## <a name="see-also"></a>请参阅
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)