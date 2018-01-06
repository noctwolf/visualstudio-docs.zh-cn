---
title: "IDebugProgramNode2::DetachDebugger_V7 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
ms.assetid: d2d4b78e-a2dd-4217-97a6-ab648fd2ee2f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: af2f9e5851e53c86fb5466e7fc2cdfe515b5fb21
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7
已弃用。 请勿使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DetachDebugger_V7 (   
   void   
);  
```  
  
```csharp  
int DetachDebugger_V7 ();  
```  
  
## <a name="return-value"></a>返回值  
 实现应始终返回`E_NOTIMPL`。  
  
## <a name="remarks"></a>备注  
  
> [!WARNING]
>  在[!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)]，此方法不再使用，应始终返回`E_NOTIMPL`。  
  
 调试器会意外退出时调用此方法。 当调用此方法时，DE 应恢复程序，就好像用户从其分离。 应发送没有更多的调试事件。 该程序应处于从调试器的另一个实例可附加的状态。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)