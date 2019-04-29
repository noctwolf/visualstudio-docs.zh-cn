---
title: IDebugPortSupplier2::CanAddPort | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 19eb4d11ab6e67384a119f11bf070a27159c1676
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62871824"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
验证端口提供程序可以添加新端口。

## <a name="syntax"></a>语法

```cpp
HRESULT CanAddPort( 
   void 
);
```

```csharp
int CanAddPort();
```

## <a name="return-value"></a>返回值
 如果可以添加端口，则返回`S_OK`; 否则为返回`S_FALSE`以指示可以将任何端口添加到此端口提供程序。

## <a name="remarks"></a>备注
 调用此方法之前调用[端口](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)方法因为后一种方法创建该端口，以及添加它，这可能一个耗时的操作。

## <a name="see-also"></a>请参阅
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)