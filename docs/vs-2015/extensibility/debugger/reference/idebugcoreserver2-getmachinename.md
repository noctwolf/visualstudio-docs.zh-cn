---
title: IDebugCoreServer2::GetMachineName |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCoreServer2::GetName
helpviewer_keywords:
- IDebugCoreServer2::GetName
ms.assetid: 693bd794-7215-4f07-8651-b57366d39953
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 406795b6991fd5a1757a099d52563b6635172a6b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49217836"
---
# <a name="idebugcoreserver2getmachinename"></a>IDebugCoreServer2::GetMachineName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取核心服务器运行的计算机的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetName(   
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetName(   
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrName`  
 [out]返回包含计算机的名称的字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)

