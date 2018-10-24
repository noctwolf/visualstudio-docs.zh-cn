---
title: IDebugProcess2::CanDetach |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::CanDetach
helpviewer_keywords:
- IDebugProcess2::CanDetach
ms.assetid: 2830f7c3-69fb-474a-97b8-5b869e38d546
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 23a4ec112c33100a2eed8e4853f5a6280a741e12
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49942135"
---
# <a name="idebugprocess2candetach"></a>IDebugProcess2::CanDetach
确定会话调试管理器 (SDM) 可以与进程分离。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CanDetach(  
   void  
);  
```  
  
```csharp  
int CanDetach();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK.`返回`S_FALSE`如果调试器无法从进程中分离。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [CanDetach](../../../extensibility/debugger/reference/idebugprogram2-candetach.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)