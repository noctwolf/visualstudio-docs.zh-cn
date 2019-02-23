---
title: IDebugPort2::GetPortName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPort2::GetPortName
helpviewer_keywords:
- IDebugPort2::GetPortName
ms.assetid: 4478b3d5-aa30-4105-8d05-e3bae2f8917a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 412e1565c62a623e20c250b6d0937cd8ff58d67f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56704418"
---
# <a name="idebugport2getportname"></a>IDebugPort2::GetPortName
获取端口名称。

## <a name="syntax"></a>语法

```cpp
HRESULT GetPortName( 
   BSTR* pbstrName
);
```

```csharp
int GetPortName( 
   out string pbstrName
);
```

#### <a name="parameters"></a>参数
 `pbstrName`

 [out]返回的端口的名称。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)