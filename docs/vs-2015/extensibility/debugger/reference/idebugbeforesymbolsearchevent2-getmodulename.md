---
title: IDebugBeforeSymbolSearchEvent2::GetModuleName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetModuleName
- IDebugBeforeSymbolSearchEvent2::GetModuleName
ms.assetid: 0b4abeac-2eaf-4b2e-a2d5-c9ec303bc869
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: caff2f20e722e8e4870bce1c5bc7d10d70033026
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62423566"
---
# <a name="idebugbeforesymbolsearchevent2getmodulename"></a>IDebugBeforeSymbolSearchEvent2::GetModuleName
检索当前正在调试的模块的名称。

## <a name="syntax"></a>语法

```cpp
HRESULT GetModuleName(
    BSTR *pbstrModuleName
);
```

```csharp
public int GetModuleName (
    string pbstrModuleName
);
```

#### <a name="parameters"></a>参数
`pbstrModuleName`

 [out]模块的名称。

## <a name="return-value"></a>返回值
如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="example"></a>示例
下面的示例演示如何实现此方法对于**CDebugBeforeSymbolSearchEventBase**对象，它公开[IDebugBeforeSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2.md)接口。

```cpp
STDMETHODIMP CDebugBeforeSymbolSearchEventBase::GetModuleName(BSTR *pbstrModuleName)
{
    HRESULT hRes = E_FAIL;

    if (m_bstrModuleName)
    {

        *pbstrModuleName = SysAllocString( m_bstrModuleName);

        if (*pbstrModuleName)
        {
            hRes = S_OK;
        }
    }

    return ( hRes );
}
```

## <a name="see-also"></a>请参阅
- [IDebugBeforeSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2.md)
