---
title: IDebugProperty2::GetReference |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetReference
helpviewer_keywords:
- IDebugProperty2::GetReference method
ms.assetid: 2fa97d9b-c3d7-478e-ba5a-a933f40a0103
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: abff655b41dbc55735b7dea2934f7d396aae5f4c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62916604"
---
# <a name="idebugproperty2getreference"></a>IDebugProperty2::GetReference
返回对该属性的值的引用。

## <a name="syntax"></a>语法

```cpp
HRESULT GetReference(
   IDebugReference2** ppReference
);
```

```csharp
int GetReference(
   out IDebugReference2 ppReference
);
```

#### <a name="parameters"></a>参数
 `ppRererence`

 [out]返回[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)对象，表示对属性的值的引用。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码，通常`E_NOTIMPL`或`E_GETREFERENCE_NO_REFERENCE`。

## <a name="see-also"></a>请参阅
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)