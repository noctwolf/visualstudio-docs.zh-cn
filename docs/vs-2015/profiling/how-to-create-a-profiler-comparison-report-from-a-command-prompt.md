---
title: 如何：从命令提示符下创建探查器比较报告 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3cb31a79af25fbe66112efd6be0aacd9b3c3820d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472431"
---
# <a name="how-to-create-a-profiler-comparison-report-from-a-command-prompt"></a>如何：从命令提示符下创建探查器比较报告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 从命令提示符创建 Profiler 比较报告](https://docs.microsoft.com/visualstudio/profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt)。  
  
可以生成 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具报告，用于比较两个分析数据（.VSP 或 .VSPS）文件的性能数据。 此报表显示显示差异、 性能回归和改进的到另一个分析会话。 报告中的值表示基于指定的首个文件的基线的增量（或变化）。 此增量是通过确定旧值（基准值）与新分析所得结果值之差计算而得。 探查器数据的比较可基于代码中的函数、应用程序中的模块、行、指令指针 (IP) 和类型。  
  
 若要列出比较类别和字段的标识符，请键入以下命令行：  
  
 **VSPerfReport /querydifftables**  *VspFileName1* *VspFileName2*  
  
 使用以下语法创建比较报告：  
  
 **VSPerfReport /diff**  `VspFileName1` *VspFileName2* [**/**`Options`]  
  
 可以向 VSPerfReport /diff 命令行添加下表中的选项。  
  
|选项|描述|  
|------------|-----------------|  
|DiffThreshold:[Value]|如果差异低于此百分比阀值，则忽略该差异。 此外，不会显示值低于此阈值的新数据。|  
|DiffTable: TableName|使用此表比较文件。 默认使用函数表。 指定 VSPerfReport /querydifftables 中列出的标识符。|  
|DiffColumn: ColumnName|使用此列对值进行比较。 默认情况下，使用独占样本百分比列。 指定 VSPerfReport /querydifftables 中列出的标识符。|



