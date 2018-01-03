---
title: "DA0002：缺少 VSPerfCorProf.dll | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.DA0002
- vs.performance.2
- vs.performance.rules.DAVsPerfCorProfMissing
- vs.performance.rules.DA0002
ms.assetid: 76e614b3-ad7e-4b92-b7be-88dc1329be1d
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 348fe328caed15da059ae5d3e9dec3b9b334e4dd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="da0002-vsperfcorprofdll-is-missing"></a>DA0002：缺少 VSPerfCorProf.dll
|||  
|-|-|  
|规则 ID|DA0002|  
|类别|分析工具使用情况|  
|分析方法|使用 VSPerfCmd 和 VSPerfASPNETCmd 命令行工具进行分析|  
|消息|收集文件时似乎未使用 VSPerfCLREnv.cmd 正确设置环境变量。 可能不会解析托管二进制文件的符号。|  
|规则类型|信息|  
  
## <a name="cause"></a>原因  
 探查器在分析运行期间找不到 VSPerfCorProf.dll。 当使用命令行工具收集探查器数据，但未使用 VSPerfCLREnv.cmd 工具初始化必要的环境变量时，将出现此警告。 如果分析工具启动时另一个探查器正在运行，也可能会触发此警告。  
  
## <a name="rule-description"></a>规则说明  
 分析运行前必须设置特定的环境变量，探查器才能解析 .NET Framework 二进制文件中的符号。 此警告表明，收集分析数据前未运行 VSPerfCLREnv.cmd 工具。 可能不会解析托管二进制文件的符号。 有关使用命令行分析工具的详细信息，请参阅[通过命令行进行分析](../profiling/using-the-profiling-tools-from-the-command-line.md)  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 分析工具中使用命令行工具分析托管应用程序时，先运行 [VSPerfCLREnv](../profiling/vsperfclrenv.md) 命令行工具，然后再开始收集数据。