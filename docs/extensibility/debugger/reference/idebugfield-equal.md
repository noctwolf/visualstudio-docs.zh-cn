---
title: IDebugField::Equal |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::Equal
helpviewer_keywords:
- IDebugField::Equal method
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ed978355aa752730cfb43390b3e4b6f80d327f83
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56693940"
---
# <a name="idebugfieldequal"></a>IDebugField::Equal
此方法将此字段与指定字段相等进行比较。

## <a name="syntax"></a>语法

```cpp
HRESULT Equal( 
   IDebugField* pField
);
```

```csharp
int Equal(
   IDebugField pField
);
```

#### <a name="parameters"></a>参数
 `pField`

 [in]要与此比较的字段。

## <a name="return-value"></a>返回值
 如果字段是相同的则返回`S_OK`。 如果字段不同，返回`S_FALSE.`否则，返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)