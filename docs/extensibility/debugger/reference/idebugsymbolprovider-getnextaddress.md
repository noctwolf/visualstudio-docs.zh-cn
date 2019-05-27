---
title: IDebugSymbolProvider::GetNextAddress |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugSymbolProvider::GetNextAddress
helpviewer_keywords:
- IDebugSymbolProvider::GetNextAddress method
ms.assetid: 704eeb94-cb13-49d1-82b6-7d83ed0f19c0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: df6c1418b49745a089b55f7d66067a54360e88fd
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66207124"
---
# <a name="idebugsymbolprovidergetnextaddress"></a>IDebugSymbolProvider::GetNextAddress
获取遵循一种方法中的给定的调试地址的调试地址。

## <a name="syntax"></a>语法

```cpp
HRESULT GetNextAddress( 
   IDebugAddress*  pAddress,
   BOOL            fStatementOnly,
   IDebugAddress** ppAddress
);
```

```csharp
int GetNextAddress( 
   IDebugAddress     pAddress,
   bool              fStatementOnly,
   out IDebugAddress ppAddress
);
```

## <a name="parameters"></a>参数
`pAddress`\
[in]给定的调试地址。

`fStatementOnly`\
[in]如果为 TRUE，则限制为单个语句的调试地址。

`ppAddress`\
[out]返回下一个调试地址。

## <a name="return-value"></a>返回值
 返回一个有效`HRESULT`，通常，则为 S_OK。

## <a name="see-also"></a>请参阅
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)