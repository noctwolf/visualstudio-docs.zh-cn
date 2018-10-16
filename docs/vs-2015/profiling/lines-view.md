---
title: “行”视图 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.view.lines
helpviewer_keywords:
- profiling tools reports, Line view
- profiling tools, Line view
- Lines view
ms.assetid: 71ec0781-6031-4e17-af09-f50226018437
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fdf3249974f2e04cc3794c3437b0d31cef7b9ef9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49205124"
---
# <a name="lines-view"></a>“行”视图
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

“行”视图仅适用于使用采样方法收集的探查器数据， 不适用于使用检测方法收集的数据。  
  
 对于采样分析数据，“行”视图标识在收集样本时直接执行的函数中的语句。 对于 .NET 内存数据，“行”视图标识分配内存的语句。  
  
 在源文件中，一个语句可以跨多个行，一行可以包含多个语句。  
  
 语句由以下数据标识：  
  
-   包含函数语句的源文件。  
  
-   包含该语句的函数。  
  
-   该语句的起始源代码行。  
  
-   该语句的起始源代码行中的字符。  
  
-   该语句的结束源代码行。  
  
-   该语句的结束源代码行中的字符。  
  
## <a name="see-also"></a>请参阅  
 [“行”视图](../profiling/lines-view-sampling-data.md)   
 [“行”视图 - 采样](../profiling/lines-view-dotnet-memory-sampling-data.md)   
 [“行”视图](../profiling/lines-view-contention-data.md)



