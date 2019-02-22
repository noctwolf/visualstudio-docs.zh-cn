---
title: IDebugDocumentContext2::GetName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDocumentContext2::GetName
helpviewer_keywords:
- IDebugDocumentContext2::GetName
ms.assetid: 546c5b2e-f166-4edb-9e61-57d797ca98a1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: caa6957f2eb34d2b125d189c87d4ca9a58126209
ms.sourcegitcommit: 845442e2b515c3ca1e4e47b46cc1cef4df4f08d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "56449974"
---
# <a name="idebugdocumentcontext2getname"></a>IDebugDocumentContext2::GetName
获取包含此文档上下文中的文档的可显示名称。

## <a name="syntax"></a>语法

```cpp
HRESULT GetName(
    GETNAME_TYPE gnType,
    BSTR*        pbstrFileName
);
```

```csharp
int GetName(
    enum_GETNAME_TYPE  gnType,
    out string         pbstrFileName
);
```

#### <a name="parameters"></a>参数
`gnType`  
[in]中的值[GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)枚举，用于指定要返回名称的类型。

`pbstrFileName`  
[out]返回的文件的名称。

## <a name="return-value"></a>返回值
如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
此方法通常将转发到调用[GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)方法，除非文档上下文写入存储文档名称本身 （如示例所示）。

## <a name="example"></a>示例
下面的示例演示如何实现此方法对于简单`CDebugContext`公开的对象[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)接口。

```cpp
HRESULT CDebugContext::GetName(GETNAME_TYPE gnType, BSTR* pbstrFileName)
{
    HRESULT hr;

    // Check for a valid file name argument.
    if (pbstrFileName)
    {
        *pbstrFileName = NULL;

        switch (gnType)
        {
            case GN_NAME:
            case GN_FILENAME:
            {
                // Copy the member file name into the local file name.
                *pbstrFileName = SysAllocString(m_sbstrFileName);
                // Check for successful copy.
                hr = (*pbstrFileName) ? S_OK : E_OUTOFMEMORY;
                break;
            }
            default:
            {
                hr = E_FAIL;
                break;
            }
        }
    }
    else
    {
        hr = E_INVALIDARG;
    }

    return hr;
}
```

## <a name="see-also"></a>请参阅
[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)  
[GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)
