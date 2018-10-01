---
title: IDebugSymbolProviderDirect::GetMethodFromAddress |Microsoft Docs
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
- IDebugSymbolProviderDirect::GetMethodFromAddress
- GetMethodFromAddress
ms.assetid: 33ffd197-1221-41bc-a9f6-f133ebdcb783
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1d89718dd47db7c0a7e38df284414830477a58b0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469104"
---
# <a name="idebugsymbolproviderdirectgetmethodfromaddress"></a>IDebugSymbolProviderDirect::GetMethodFromAddress
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugSymbolProviderDirect::GetMethodFromAddress](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugsymbolproviderdirect-getmethodfromaddress)。  
  
检索有关指定的调试地址处的方法的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetMethodFromAddress(  
   IDebugAddress* pAddress,  
   GUID*          pGuid,  
   DWORD*         pAppID,  
   _mdToken*      pTokenClass,  
   _mdToken*      pTokenMethod,  
   DWORD*         pdwOffset,  
   DWORD*         pdwVersion  
);  
```  
  
```csharp  
int GetMethodFromAddress(  
   IDebugAddress pAddress,  
   out Guid      pGuid,  
   out uint      pAppID,  
   out uint      pTokenClass,  
   out uint      pTokenMethod,  
   out uint      pdwOffset,  
   out uint      pdwVersion  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAddress`  
 [in]调试由表示的地址[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)接口。  
  
 `pGuid`  
 [out]该模块的唯一标识符。  
  
 `pAppID`  
 [out]应用程序域的标识符。  
  
 `pTokenClass`  
 [out]令牌，它表示包含类。  
  
 `pTokenMethod`  
 [out]标记，表示该模块。  
  
 `pdwOffset`  
 [out]以字节为单位从开头的偏移量`pAddress`参数。  
  
 `pdwVersion`  
 [out]该方法的版本号。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSymbolProviderDirect](../../../extensibility/debugger/reference/idebugsymbolproviderdirect.md)

