---
title: "IDebugCustomAttributeQuery::GetCustomAttributeByName |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugCustomAttributeQuery::GetCustomAttributeByName
- GetCustomAttributeByName
ms.assetid: 6779727c-d10a-4abe-9acd-d0a1eb0737e7
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c49bf8f1598f2229345f7a87673b639f6cdfc76a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcustomattributequerygetcustomattributebyname"></a>IDebugCustomAttributeQuery::GetCustomAttributeByName
检索在给定其名称的自定义特性。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCustomAttributeByName(  
   LPCOLESTR pszCustomAttributeName,  
   BYTE*     ppBlob,  
   DWORD*    pdwLen  
);  
```  
  
```csharp  
int GetCustomAttributeByName(  
   string    pszCustomAttributeName,  
   ref int[] ppBlob,  
   out uint  pdwLen  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszCustomAttributeName`  
 [in]自定义特性的名称。  
  
 `ppBlob`  
 [在中，out]包含自定义属性数据的字节数组。  
  
 `pdwLen`  
 [out]以字节为单位的长度`ppBlob`参数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 如果不存在自定义特性，将返回`S_FALSE`。 否则，返回错误代码。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于**CDebugClassFieldSymbol**公开的对象[IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)接口。  
  
```cpp  
HRESULT CDebugClassFieldSymbol::GetCustomAttributeByName(  
    LPCOLESTR pszCustomAttributeName,  
    BYTE *pBlob,  
    DWORD *pdwLen  
)  
{  
    HRESULT hr = S_FALSE;  
    CComPtr<IMetaDataImport> pMetadata;  
    mdToken token = mdTokenNil;  
    CComPtr<IDebugField> pField;  
    CComPtr<IDebugCustomAttributeQuery> pCA;  
  
    ASSERT(IsValidWideStringPtr(pszCustomAttributeName));  
    ASSERT(IsValidWritePtr(pdwLen, ULONG*));  
  
    METHOD_ENTRY( CDebugClassFieldSymbol::GetCustomAttributeByName );  
  
    IfFalseGo( pszCustomAttributeName && pdwLen, E_INVALIDARG );  
  
    IfFailGo( m_spSH->GetMetadata( m_spAddress->GetModule(), &pMetadata ) );  
  
    IfFailGo( CDebugCustomAttribute::GetTokenFromAddress( m_spAddress, &token) );  
    IfFailGo( CDebugCustomAttribute::GetCustomAttributeByName( pMetadata,  
              token,  
              pszCustomAttributeName,  
              pBlob,  
              pdwLen ) );  
Error:  
  
    METHOD_EXIT( CDebugClassFieldSymbol::GetCustomAttributeByName, hr );  
    return hr;  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [IDebugCustomAttributeQuery](../../../extensibility/debugger/reference/idebugcustomattributequery.md)