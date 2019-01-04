---
title: SetWefProcessId 方法
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 3ccce49992073f11245929bf7af0b966537bd079
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53886145"
---
# <a name="setwefprocessid-method"></a>SetWefProcessId 方法
  提供将运行 Web 扩展框架 (WEF) 内容的进程标识符。  
  
## <a name="syntax"></a>语法  
  
```csharp  
HRESULT SetWefProcessId(  
    [in] DWORD dwProcessId  
);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|*dwProcessId*|将用于运行 WEF 内容进程标识符。|  
  
## <a name="return-value"></a>返回值  
 HRESULT 值，指示方法是否已成功完成。  
  
## <a name="remarks"></a>备注  
 创建的 WEF 内容过程之后但在任何 WEF 内容运行之前，必须调用此方法。  
  
 如果你想要将调试器附加到 WEF 内容进程的开发环境，环境必须在实现此方法中执行此操作。  
