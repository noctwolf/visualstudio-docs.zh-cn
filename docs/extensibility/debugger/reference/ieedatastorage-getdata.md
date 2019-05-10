---
title: IEEDataStorage::GetData | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEDataStorage::GetData
helpviewer_keywords:
- IEEDataStorage::GetData
ms.assetid: 4d384039-73d4-40b4-ace6-a2474c546397
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8d9c00f21ab39d5785acb0090b16b5b1fc193699
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65224187"
---
# <a name="ieedatastoragegetdata"></a>IEEDataStorage::GetData
从对象检索指定的字节数。

## <a name="syntax"></a>语法

```cpp
HRESULT GetData(
   ULONG  dataSize,
   ULONG* sizeGotten,
   BYTE*  data
);
```

```csharp
int GetData(
   uint     dataSize,
   out uint sizeGotten,
   byte[]   data
);
```

## <a name="parameters"></a>参数
 `dataSize`\

 [in]要检索的字节数 (`data`数组必须至少容纳此数目的字节数)。

 `sizeGotten`\

 [out]返回实际检索的字节的数。

 `data`\

 [in、 out]若要使用请求的数据填充的数组。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 建议的使用此方法是将所有数据字节都检索到本地数组，因为没有方法来跳过的检索过程中的字节。 在此情况下，参数`dataSize`应返回的值[GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)方法。

## <a name="see-also"></a>请参阅
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
- [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)