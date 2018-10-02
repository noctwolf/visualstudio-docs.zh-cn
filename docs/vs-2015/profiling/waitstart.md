---
title: WaitStart | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e1e452fb46af37778a94dee271adf47a1255e1b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479316"
---
# <a name="waitstart"></a>WaitStart
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[WaitStart](https://docs.microsoft.com/visualstudio/profiling/waitstart)。  
  
仅当探查器已初始化，或已超过指定秒数时，WaitStart 选项才使 VSPerfCmd.exe Start 子命令返回。 默认情况下，Start 命令将立即返回。 如果 Start 子命令在未初始化探查器的情况下就返回，则将返回一个错误。 如果未指定秒数，Start 命令将无限期等待。  
  
 WaitStart 选项在批处理文件中十分有用，可确保探查器已经过初始化。  
  
## <a name="syntax"></a>语法  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>参数  
 `Seconds`  
 从 Start 子命令返回前要等待的秒数。  
  
## <a name="required-options"></a>必需选项  
 WaitStart 选项仅可与 Start 子命令一起使用。  
  
 **Output:** `filename`  
 指定输出文件名。  
  
## <a name="remarks"></a>备注  
  
## <a name="example"></a>示例  
 在此批处理示例中，Start 命令将等待 5 秒，探查器才会初始化。  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```



