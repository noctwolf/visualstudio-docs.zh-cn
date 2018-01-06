---
title: "IDebugDocumentContext2::GetLanguageInfo |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentContext2::GetLanguageInfo
helpviewer_keywords: IDebugDocumentContext2::GetLanguageInfo
ms.assetid: 6a212ee5-414c-4eb5-ab11-19db1786943d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3ef815ecde171819fd32ae4a3874fd035492c885
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentcontext2getlanguageinfo"></a>IDebugDocumentContext2::GetLanguageInfo
获取与此文档上下文关联的语言。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetLanguageInfo(   
   BSTR* pbstrLanguage,  
   GUID* pguidLanguage  
);  
```  
  
```csharp  
int GetLanguageInfo(   
   out string pbstrLanguage,  
   out Guid   pguidLanguage  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrLanguage`  
 [out]返回实现此文档上下文的代码的语言的名称。  
  
 `pguidLanguage`  
 [out]返回实现此文档上下文的代码的语言的 GUID。 例如，`guidVBScriptLang` 或 `guidCPPLang`。 此 GUID 并不局限于由提供的语言[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于简单`CDebugContext`公开的对象[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)接口。  
  
```cpp  
HRESULT CDebugContext::GetLanguageInfo(BSTR* pbstrLanguage, GUID* pguidLanguage)    
{    
   HRESULT hr;    
  
   // Check for a valid language argument pointers.    
   if (pbstrLanguage && pguidLanguage)    
   {    
      *pguidLanguage = GUID_NULL;    
      *pbstrLanguage = SysAllocString(L"Batch File");    
      if (*pbstrLanguage)    
      {    
         *pguidLanguage = guidBatLang;    
         hr = S_OK;    
      }    
      else    
      {    
         hr = E_OUTOFMEMORY;    
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