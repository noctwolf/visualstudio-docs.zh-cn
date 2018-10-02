---
title: IDebugBinder3::GetTypeArguments |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugBinder3::GetTypeArguments
helpviewer_keywords:
- IDebugBinder3::GetTypeArguments method
ms.assetid: fa0c37a7-327f-463e-9a9d-bb3f534584cb
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b82c5befe302c88e9f687bd2e6be7195dc4757cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482512"
---
# <a name="idebugbinder3gettypearguments"></a>IDebugBinder3::GetTypeArguments
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugBinder3::GetTypeArguments](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder3-gettypearguments)。

此方法检索与此对象关联的参数类型的列表。

## <a name="syntax"></a>语法

```cpp
HRESULT GetTypeArguments(
   UINT          skip,
   UINT          count,
   IDebugField** ppFields,
   UINT*         pFetched
);
```

```csharp
int GetTypeArguments(
   uint          skip,
   uint          count,
   IDebugField[] ppFields,
   out uint      pFetched
);
```

#### <a name="parameters"></a>参数

 `skip`

 [in]若要获取参数类型之前跳过的字段数。

 `count`

 [in]要返回的参数字段数 (还指定的大小`ppFields`数组)。

 `ppFields`

 [in、 out]会在此方法返回填充的字段的数组。

 `pFetched`

 [out]返回的自变量类型的字段数实际上 （可选）。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 自变量类型的数即可获得事先[GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)。

## <a name="see-also"></a>请参阅

- [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)
- [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)