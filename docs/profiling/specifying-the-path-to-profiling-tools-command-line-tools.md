---
title: 指定分析工具命令行工具的路径 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e25d5052cbc70e4a45040f8ebadb8cb36daa053
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>指定分析工具命令行工具的路径
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 分析工具命令行工具的路径不添加到 PATH 环境变量中。 在 32 位计算机上，这些工具位于单个目录中。 64 位计算机上有这些分析工具的 32 位和 64 位版本。  
  
## <a name="32-bit-computers"></a>32 位计算机  
 在 32 位计算机上，默认的探查器工具目录为 *驱动器*\Program Files\Microsoft Visual Studio 11.0\Team Tools\Performance Tools。  
  
## <a name="64-bit-computers"></a>64 位计算机  
 在 64 位计算机上，根据被分析应用程序的目标平台指定路径。  
  
-   对于 32 位应用程序，默认的探查器工具目录为：  
  
     *驱动器*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools  
  
-   对于 64 位应用程序，默认的探查器工具目录为：  
  
     *驱动器*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\x64