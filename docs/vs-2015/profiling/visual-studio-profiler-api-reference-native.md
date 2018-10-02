---
title: Visual Studio 探查器 API 参考（本机）| Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance tools, API
- Profiler, API
ms.assetid: a0c3be92-c263-4678-9fb9-bafead3bd5f5
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74a66580cf7fb0b5fb998442fe59a3cb601da437
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471233"
---
# <a name="visual-studio-profiler-api-reference-native"></a>Visual Studio 探查器 API 参考（本机）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[Visual Studio Profiler API 参考 （本机）](https://docs.microsoft.com/visualstudio/profiling/visual-studio-profiler-api-reference-native)。  
  
Visual Studio 探查器 API 允许你以编程方式控制收集的数据量，并在分析期间插入时间戳和分析标记。 若要使用本机 API，请包含 VSPerf.h 头文件，并在项目中添加 VSPerf.lib。  
  
> [!NOTE]
>  默认情况下，VSPerf.h 和 VSPerf.lib 位于\<驱动器>：\Program Files\Microsoft Visual Studio 9\Team Tools\Performance Tools\PerfSDK 目录中。  
  
## <a name="in-this-section"></a>本节内容  
 [CommentMarkAtProfile](../profiling/commentmarkatprofile.md)  
  
 [CommentMarkProfile](../profiling/commentmarkprofile.md)  
  
 [MarkProfile](../profiling/markprofile.md)  
  
 [NameProfile](../profiling/nameprofile.md)  
  
 [ResumeProfile](../profiling/resumeprofile.md)  
  
 [StartProfile](../profiling/startprofile.md)  
  
 [StopProfile](../profiling/stopprofile.md)  
  
 [SuspendProfile](../profiling/suspendprofile.md)  
  
 [PROFILE_CURRENTID](../profiling/profile-currentid.md)  
  
## <a name="see-also"></a>请参阅  
 [分析工具 API](../profiling/profiling-tools-apis.md)   
 [演练：使用探查器 API](../profiling/walkthrough-using-profiler-apis.md)



