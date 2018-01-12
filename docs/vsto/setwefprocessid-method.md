---
title: "SetWefProcessId 方法 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5c27588eb6d09c0565b4b4d8faec52239ef792f7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="setwefprocessid-method"></a>SetWefProcessId 方法
  提供将运行 Web 扩展框架 (WEF) 内容的进程标识符。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
  