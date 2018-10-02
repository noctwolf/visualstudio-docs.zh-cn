---
title: IDebugComPlusSymbolProvider::GetNameFromToken |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugComPlusSymbolProvider::GetNameFromToken
- GetNameFromToken
ms.assetid: 6e8cf468-5fd1-4655-93ed-88828d6068b7
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e7a10208f5bbb7bd3803b0cd7e0a417c18b8ba3e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476706"
---
# <a name="idebugcomplussymbolprovidergetnamefromtoken"></a>IDebugComPlusSymbolProvider::GetNameFromToken
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugComPlusSymbolProvider::GetNameFromToken](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcomplussymbolprovider-getnamefromtoken)。  
  
返回与给定其元数据对象的指定标记关联的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetNameFromToken (  
   IUnknown* pMetadataImport,  
   DWORD     dwToken,  
   BSTR*     pbstrName  
);  
```  
  
```csharp  
int GetNameFromToken (  
   object     pMetadataImport,  
   uint       dwToken,  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pMetadataImport`  
 [in]包含元数据信息的对象。  
  
 `dwToken`  
 [in]若要将名为的标记。  
  
 `pbstrName`  
 [out]对应于令牌的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于**CDebugSymbolProvider**对象，它公开[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)接口。  
  
```cpp#  
HRESULT CDebugSymbolProvider::GetNameFromToken(  
    IUnknown* pMetadataImport,  
    DWORD dwToken,  
    BSTR* pbstrName  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<IMetaDataImport> pMetaData;  
  
    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));  
    ASSERT(IsValidInterfacePtr(pMetadataImport, IUnknown));  
  
    METHOD_ENTRY(CDebugSymbolProvider::GetNameFromToken);  
  
    IfFalseGo( pMetadataImport && pbstrName, E_INVALIDARG );  
  
    *pbstrName = NULL;  
    IfFailGo( pMetadataImport->QueryInterface( IID_IMetaDataImport,  
              (void**) &pMetaData ) );  
  
    switch ( TypeFromToken(dwToken) )  
    {  
        case mdtModule:  
            IfFailGo( GetModuleName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtTypeDef:  
            IfFailGo( GetTypeName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtFieldDef:  
            IfFailGo( GetFieldName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtMethodDef:  
            IfFailGo( GetMethodName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtEvent:  
            IfFailGo( GetEventName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtProperty:  
            IfFailGo( GetPropertyName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        case mdtAssembly:  
            IfFailGo( GetAssemblyName( pMetaData, dwToken, pbstrName) );  
            break;  
  
        default:  
            ASSERT(!"Unsupported token passed to GetNameFromToken");  
            hr = E_FAIL;  
            break;  
    }  
  
Error:  
  
    METHOD_EXIT(CDebugSymbolProvider::GetNameFromToken, hr);  
    return hr;  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)

