---
title: IPropertyProxyEESide::CreateReplacementObject |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::CreateReplacementObject
helpviewer_keywords:
- IPropertyProxyEESide::CreateReplacementObject
ms.assetid: 0cfe79b8-c3f1-48b0-a225-e39dee2c92fe
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 03bfeeb30fad4f332a3a747dcf8468c4fb39ef56
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62914033"
---
# <a name="ipropertyproxyeesidecreatereplacementobject"></a>IPropertyProxyEESide::CreateReplacementObject
创建数据对象的副本特定于表达式计算器 (EE)。

## <a name="syntax"></a>语法

```cpp
HRESULT CreateReplacementObject(
   IEEDataStorage*  dataIn,
   IEEDataStorage** dataOut
);
```

```csharp
int CreateReplacementObject(
   IEEDataStorage     dataIn,
   out IEEDataStorage dataOut
);
```

#### <a name="parameters"></a>参数
 `dataIn`

 [in][IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)包含要复制的数据对象。

 `dataOut`

 [out]返回一个新`IEEDataStorage`对象。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 此方法提供[IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)对象，表示一个字节数组。 EE 通常没有实现此传入数据对象。 但是，此方法返回的对象始终通过 EE，它允许 EE 实现实现`IEEDataStorage`上任何类所需的接口。

 请注意，数据提供传入的`IEEDataStorage`对象必须是相同的数据中的传出`IEEDataStorage`对象。

## <a name="see-also"></a>请参阅
- [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)