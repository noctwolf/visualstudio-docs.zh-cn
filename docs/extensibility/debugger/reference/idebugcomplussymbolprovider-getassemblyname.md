---
title: IDebugComPlusSymbolProvider::GetAssemblyName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugComPlusSymbolProvider::GetAssemblyName
- GetAssemblyName
ms.assetid: a08cd609-b9b9-47bd-bf73-cbf851285907
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2a8db1926fe6c4480c136d5d62ca523667530478
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66206537"
---
# <a name="idebugcomplussymbolprovidergetassemblyname"></a>IDebugComPlusSymbolProvider::GetAssemblyName
检索给定其模块和应用程序域的程序集的名称。

## <a name="syntax"></a>语法

```cpp
HRESULT GetAssemblyName(
    ULONG32 ulAppDomainID,
    GUID    guidModule,
    BSTR*   pbstrName
);
```

```csharp
int GetAssemblyName(
    uint   ulAppDomainID,
    Guid   guidModule,
    string pbstrName
);
```

## <a name="parameters"></a>参数
`ulAppDomainID`\
[in]应用程序域标识符。

`guidModule`\
[in]该模块的唯一标识符。

`pbstrName`\
[out]返回的程序集的名称。

## <a name="return-value"></a>返回值
如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="example"></a>示例
下面的示例演示如何实现此方法对于**CDebugSymbolProvider**对象，它公开[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)接口。

```cpp
HRESULT CDebugSymbolProvider::GetAssemblyName(
    ULONG32 ulAppDomainID,
    GUID guidModule,
    BSTR* pbstrName
)
{
    HRESULT hr = S_OK;
    Module_ID idModule(ulAppDomainID, guidModule);
    CComPtr<IMetaDataImport> pMetadata;

    METHOD_ENTRY( CDebugSymbolProvider::GetMetadataForModule );

    IfFalseGo( pbstrName, E_INVALIDARG );
    *pbstrName = NULL;

    IfFailGo( GetMetadata( idModule, &pMetadata ) );
    IfFailGo( GetAssemblyName( pMetadata, 0, pbstrName ) );

Error:

    METHOD_EXIT( CDebugSymbolProvider::GetMetadataForModule, hr );
    return hr;
}
```

## <a name="see-also"></a>请参阅
- [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)
