---
title: IDebugProgram2::GetDebugProperty |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetDebugProperty
helpviewer_keywords:
- IDebugProgram2::GetDebugProperty
ms.assetid: d194224e-f0e6-46ab-85d4-9e2639e28946
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 660d8f40b2a9d3ead0010c1139a3d887d0524aa9
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212318"
---
# <a name="idebugprogram2getdebugproperty"></a>IDebugProgram2::GetDebugProperty
获取该程序的属性。

## <a name="syntax"></a>语法

```cpp
HRESULT GetDebugProperty( 
   IDebugProperty2** ppProperty
);
```

```csharp
int GetDebugProperty( 
   out IDebugProperty2 ppProperty
);
```

## <a name="parameters"></a>参数
`ppProperty`\
[out]返回[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)对象，表示该程序的属性。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 此方法返回的属性是特定于该程序。 如果该程序需要返回多个属性，则[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)此方法返回的对象是一个容器的其他属性和调用[EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)方法将返回所有属性的列表。

 程序可能会公开任何数量和类型的其他属性，可以通过描述`IDebugProperty2`接口。 IDE 可能会显示通过泛型属性浏览器用户界面的其他程序属性。

## <a name="see-also"></a>请参阅
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)