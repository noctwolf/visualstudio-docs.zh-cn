---
title: IDebugProgramPublisher2::SetDebuggerPresent |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgramPublisher2::SetDebuggerPresent
helpviewer_keywords:
- IDebugProgramPublisher2::SetDebuggerPresent
ms.assetid: c88c3ff4-3632-4199-b5de-83c6d21bcf75
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 86351bda9d221200e9c84c2e1fb3590c451c57e8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481807"
---
# <a name="idebugprogrampublisher2setdebuggerpresent"></a>IDebugProgramPublisher2::SetDebuggerPresent
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProgramPublisher2::SetDebuggerPresent](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogrampublisher2-setdebuggerpresent)。  
  
告知调试器存在并且运行程序发布服务器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetDebuggerPresent(  
   BOOL fDebuggerPresent  
);  
```  
  
```csharp  
int SetDebuggerPresent(  
   int fDebuggerPresent  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fDebuggerPresent`  
 [in]非零 (`TRUE`) 如果存在调试程序，则为零 (`FALSE`) 如果不是。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 从返回的数据中反映出来是否存在调试器[GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)方法： 存在返回的值是设置，或者通过调用之前清除`SetDebuggerPresent`方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)

