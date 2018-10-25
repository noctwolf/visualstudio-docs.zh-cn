---
title: IDebugComPlusSymbolProvider::IsFunctionStale |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugComPlusSymbolProvider::IsFunctionStale
ms.assetid: dcffc090-4ed8-47b2-ba51-bce1a6b6428d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bbd68a17e940a7f0f183b49c8194439fd6c21d92
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49893450"
---
# <a name="idebugcomplussymbolproviderisfunctionstale"></a>IDebugComPlusSymbolProvider::IsFunctionStale
确定是否在指定的调试地址函数被视为过时。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsFunctionStale(  
   IDebugAddress* pAddress  
);  
```  
  
```csharp  
int IsFunctionStale(  
   IDebugAddress pAddress  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAddress`  
 [in]由表示的调试地址[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口。 该地址必须是 METHOD_ADDRESS。  
  
## <a name="return-value"></a>返回值  
 如果该函数被视为过时，将返回`S_OK`。 如果该函数不是过时的则返回`S_FALSE`。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于**CDebugSymbolProvider**对象，它公开[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)接口。  
  
```cpp  
HRESULT CDebugSymbolProvider::IsFunctionStale(  
    IDebugAddress* pAddress  
)  
{  
    HRESULT hr = S_OK;  
    CDEBUG_ADDRESS address;  
    CComPtr<CModule> pModule;  
  
    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));  
    ASSERT(IsValidInterfacePtr(pAddress, IDebugAddress));  
  
    METHOD_ENTRY( CDebugSymbolProvider::IsFunctionStale );  
  
    IfFalseGo( pAddress, S_FALSE );  
    IfFailGo( pAddress->GetAddress( &address ) );  
  
    ASSERT(address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD);  
    IfFalseGo( address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD, S_FALSE );  
  
    IfFailGo( GetModule( address.GetModule(), &pModule) );  
  
    if (!pModule->IsFunctionStale( address.addr.addr.addrMethod.tokMethod,  
                                   address.addr.addr.addrMethod.dwVersion ))  
    {  
  
        // S_FALSE indicates the function is not stale  
  
        hr = S_FALSE;  
    }  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::IsFunctionStale, hr );  
  
    if (!SUCCEEDED(hr))  
    {  
        hr = S_FALSE;  
    }  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)