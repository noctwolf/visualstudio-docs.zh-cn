---
title: SetWefProcessId 方法
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b426237816bfee53e7c3e50c19e29168b27e16e1
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693427"
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
 创建 WEF 内容进程之后但尚未运行任何 WEF 内容之前，必须调用此方法。  
  
 如果你想要将调试器附加到 WEF 内容进程的开发环境，环境必须实现此方法中执行此操作。  
  
  