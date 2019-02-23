---
title: IDebugCoreServer2::GetMachineName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer2::GetName
helpviewer_keywords:
- IDebugCoreServer2::GetName
ms.assetid: 693bd794-7215-4f07-8651-b57366d39953
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 908f234aad481b9ce6dc646e78741b26131d9c1c
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717762"
---
# <a name="idebugcoreserver2getmachinename"></a>IDebugCoreServer2::GetMachineName
获取核心服务器运行的计算机的名称。

## <a name="syntax"></a>语法

```cpp
HRESULT GetName( 
   BSTR* pbstrName
);
```

```csharp
int GetName( 
   out string pbstrName
);
```

#### <a name="parameters"></a>参数
 `pbstrName`

 [out]返回包含计算机的名称的字符串。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)