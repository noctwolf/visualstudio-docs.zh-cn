---
title: IDebugComPlusSymbolProvider::GetSymUnmanagedReader |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugComPlusSymbolProvider::GetSymUnmanagedReader
- GetSymUnmanagedReader
ms.assetid: 8f1c1627-217f-4405-8141-7a2eb80310a5
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f63ede5a414661d2d171186bbc451b996e54317f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49268302"
---
# <a name="idebugcomplussymbolprovidergetsymunmanagedreader"></a>IDebugComPlusSymbolProvider::GetSymUnmanagedReader
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

检索要使用由非托管代码的符号读取器。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetSymUnmanagedReader(  
   ULONG32    ulAppDomainID,  
   GUID       guidModule,  
   IUnknown** ppSymUnmanagedReader  
);  
```  
  
```csharp  
int GetSymUnmanagedReader(  
   uint       ulAppDomainID,  
   Guid       guidModule,  
   out object ppSymUnmanagedReader  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ulAppDomainID`  
 [in]应用程序域的标识符。  
  
 `guidModule`  
 [in]该模块的唯一标识符。  
  
 `ppSymUnmanagedReader`  
 [out]返回该对象表示的符号读取器。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于**CDebugSymbolProvider**对象，它公开[IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)接口。  
  
```cpp#  
HRESULT CDebugSymbolProvider::GetSymUnmanagedReader(  
    ULONG32 ulAppDomainID,  
    GUID guidModule,  
    IUnknown ** ppSymUnmanagedReader  
)  
{  
    HRESULT hr = S_OK;  
    CComPtr<CModule> pModule;  
    Module_ID idModule(ulAppDomainID, guidModule);  
  
    METHOD_ENTRY( CDebugSymbolProvider::GetSymUnmanagedReader );  
  
    IfFailGo( GetModule( idModule, &pModule ) );  
    IfFailGo( pModule->GetSymReader((ISymUnmanagedReader**) ppSymUnmanagedReader) );  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::GetSymUnmanagedReader, hr );  
    return hr;  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)

