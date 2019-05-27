---
title: IDebugProperty2::GetParent | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetParent
helpviewer_keywords:
- IDebugProperty2::GetParent
ms.assetid: 58780469-fe25-4d84-9187-67940ca0767f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 751fb9cea09826c78067c9d44e81b556355e94d1
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211511"
---
# <a name="idebugproperty2getparent"></a>IDebugProperty2::GetParent
获取一个属性的父属性。

## <a name="syntax"></a>语法

```cpp
HRESULT GetParent ( 
   IDebugProperty2** ppParent
);
```

```csharp
int GetParent ( 
   out IDebugProperty2 ppParent
);
```

## <a name="parameters"></a>参数
`ppParent`\
[out]返回[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)对象，表示属性的父级。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则返回错误代码。 返回`S_GETPARENT_NO_PARENT`如果没有父级。

## <a name="see-also"></a>请参阅
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)