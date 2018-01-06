---
title: "IDebugReference2::SetValueAsString |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugReference2::SetValueAsString
helpviewer_keywords: IDebugReference2::SetValueAsString
ms.assetid: 9a508ced-fd54-44f5-bb42-ec15c80384d7
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8a5c5bca596ebf463841c0e2dcb1c6ba1cce71b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugreference2setvalueasstring"></a>IDebugReference2::SetValueAsString
设置的值从字符串的引用。 留待将来使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetValueAsString (   
   LPCOLESTR pszValue,  
   DWORD     dwRadix,  
   DWORD     dwTimeout  
);  
```  
  
```csharp  
int SetValueAsString (   
   string pszValue,  
   uint   dwRadix,  
   uint   dwTimeout  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszValue`  
 [in]字符串形式的值。  
  
 `dwRadix`  
 [in]用于设置格式的任何数字信息基数。  
  
 `dwTimeout`  
 [in]以毫秒为单位，从此方法返回前等待的最长时间。 使用`INFINITE`无限期等待。  
  
## <a name="return-value"></a>返回值  
 始终返回 `E_NOTIMPL`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)