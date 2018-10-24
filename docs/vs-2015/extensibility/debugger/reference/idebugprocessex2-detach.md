---
title: IDebugProcessEx2::Detach |Microsoft Docs
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
- IDebugProcessEx2::Detach
helpviewer_keywords:
- IDebugProcessEx2::Detach method
ms.assetid: 66d54c2c-9302-47c8-9975-f30ed988ab29
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: adb466ee030700c938c59781d97b66be5ba5b30d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49921790"
---
# <a name="idebugprocessex2detach"></a>IDebugProcessEx2::Detach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此方法将通知该过程在会话不再调试进程。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Detach(   
   IDebugSession2* pSession  
);  
```  
  
```csharp  
int Detach(  
   IDebugSession2 pSession  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pSession`  
 [in]一个值，唯一标识要分离从的此进程的会话。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 接口传入`pSession`仅作为 cookie 处理，用于唯一标识会话调试管理器最初的值附加到此过程; 上提供的接口的方法不起作用。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)

