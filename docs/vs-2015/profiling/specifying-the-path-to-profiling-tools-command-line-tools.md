---
title: 指定分析工具命令行工具的路径 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ccf7739a8efacacec3c48b47a59d6db6f6e8de8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471011"
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>指定分析工具命令行工具的路径
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[指定分析工具命令行工具的路径](https://docs.microsoft.com/visualstudio/profiling/specifying-the-path-to-profiling-tools-command-line-tools)。  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具命令行工具的路径不添加到 PATH 环境变量中。 在 32 位计算机上，这些工具位于单个目录中。 64 位计算机上有这些分析工具的 32 位和 64 位版本。  
  
## <a name="32-bit-computers"></a>32 位计算机  
 在 32 位计算机上，默认的探查器工具目录为 *驱动器*\Program Files\Microsoft Visual Studio 11.0\Team Tools\Performance Tools。  
  
## <a name="64-bit-computers"></a>64 位计算机  
 在 64 位计算机上，根据被分析应用程序的目标平台指定路径。  
  
-   对于 32 位应用程序，默认的探查器工具目录为：  
  
     *驱动器*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools  
  
-   对于 64 位应用程序，默认的探查器工具目录为：  
  
     *驱动器*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\x64



