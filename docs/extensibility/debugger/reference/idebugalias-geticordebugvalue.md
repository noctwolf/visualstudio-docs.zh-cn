---
title: IDebugAlias::GetICorDebugValue | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::GetICorDebugValue
helpviewer_keywords:
- IDebugAlias::GetICorDebugValue method
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 50fb7800c4446e7d13334957ee9f5f6534f254bf
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66338216"
---
# <a name="idebugaliasgeticordebugvalue"></a>IDebugAlias::GetICorDebugValue
检索表示与此别名关联的值的托管的代码接口。

## <a name="syntax"></a>语法

```cpp
HRESULT GetICorDebugValue(
   IUnknown** ppUnk
);
```

```csharp
int GetICorDebugValue(
   out object ppUnk
);
```

## <a name="parameters"></a>参数
`ppUnk`\
[out]`IUnknown`接口，表示与此别名关联的值。 此接口可以查询有关`ICorDebugValue`接口。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 此方法仅适用于托管值 (`ICorDebugValue`是一个接口中可用[!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)]中定义， [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] cordebug.idl 文件中的 SDK)。

## <a name="see-also"></a>请参阅
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)