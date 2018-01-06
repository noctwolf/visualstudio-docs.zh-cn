---
title: "IDebugProgram2::GetENCUpdate |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::GetENCUpdate
helpviewer_keywords: IDebugProgram2::GetENCUpdate
ms.assetid: 9832aac8-6320-4fd8-91dd-2a0852febb00
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 974b76bafabaa3621ffb71a530b67e9643436c04
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2getencupdate"></a>IDebugProgram2::GetENCUpdate
此方法获取此程序的编辑并继续 (ENC) 更新。 自定义调试引擎始终返回`E_NOTIMPL`。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetENCUpdate(   
   IUnknown** ppUpdate  
);  
```  
  
```csharp  
int GetENCUpdate(  
   out object ppUpdate  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppUpdate`  
 [out]返回可以用于更新此程序的内部接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
> [!NOTE]
>  自定义调试引擎应始终返回`E_NOTIMPL`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)