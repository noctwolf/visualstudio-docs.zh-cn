---
title: IDebugArrayField::GetRank |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1c091c7696867f369262a81259105dcf23fbe4c9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877734"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
获取秩或维数的数组。

## <a name="syntax"></a>语法

```cpp
HRESULT GetRank( 
   DWORD* pdwRank
);
```

```csharp
int GetRank(
   out uint pdwRank
);
```

#### <a name="parameters"></a>参数
 `pdwRank`

 [out]返回排名。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 数组的秩对应于维度的数目。 在C++和C#，多维数组实际上是数组的数组，因此可被视为只是一个一维数组 (和`GetRank`方法始终返回 1)。 在中[!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]，但是，多维数组的处理方式不同并这样的数组的秩反映的维数 (和`GetRank`方法始终返回维度的数目)。

## <a name="see-also"></a>请参阅
- [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)