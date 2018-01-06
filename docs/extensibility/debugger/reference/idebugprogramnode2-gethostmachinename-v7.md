---
title: "IDebugProgramNode2::GetHostMachineName_V7 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNode2::GetHostMachineName
helpviewer_keywords:
- IDebugProgramNode2::GetHostMachineName_V7
- IDebugProgramNode2::GetHostMachineNameIDebugProgramNode2::GetHostMachineName
ms.assetid: a992f2c9-f68b-4146-8cc2-027753bf7ce6
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 89d88203f4306971128a233237f4d8c7d56054d6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramnode2gethostmachinenamev7"></a>IDebugProgramNode2::GetHostMachineName_V7
已弃用。 请勿使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetHostMachineName_V7 (   
   BSTR* pbstrHostMachineName  
);  
```  
  
```csharp  
int GetHostMachineName_V7 (   
   out string pbstrHostMachineName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrHostMachineName`  
 [out]返回在其中运行该程序的计算机的名称。  
  
## <a name="return-value"></a>返回值  
 实现应始终返回`E_NOTIMPL`。  
  
## <a name="remarks"></a>备注  
  
> [!WARNING]
>  在[!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)]，此方法不再使用，应始终返回`E_NOTIMPL`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)