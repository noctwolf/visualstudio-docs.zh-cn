---
title: TargetCLR | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 915ca4a859b4c80f785262f1c05698c4d34a683b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470158"
---
# <a name="targetclr"></a>TargetCLR
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[TargetCLR](https://docs.microsoft.com/visualstudio/profiling/targetclr)。  
  
“TargetCLR”选项指定应用程序中加载 CLR 的多个版本时要分析的公共语言运行时 (CLR) 的版本。  
  
 默认情况下，[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具以应用程序加载的第一个 CLR 版本为目标。  
  
## <a name="syntax"></a>语法  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>参数  
 `ClrVersion`  
 CLR 的版本号。 使用版本格式 vN.N.NNNNN。  
  
## <a name="required-options"></a>必需选项  
 “TargetCLR”选项只能与“启动”或“附加”选项一起使用。  
  
 **Launch：**`AppName`  
 启动指定的应用程序并开始分析。  
  
 **Attach:** `PID`  
 开始分析指定的进程。  
  
## <a name="example"></a>示例  
 在此示例中，使用 TargetCLR 选项以确保分析 CLR 版本 4.0.11003。  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```



