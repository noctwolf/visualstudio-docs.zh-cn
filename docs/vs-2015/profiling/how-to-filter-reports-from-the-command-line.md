---
title: 如何：从命令行筛选报告 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14be02ecf293cfb141b671917a715c8013009d2e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471206"
---
# <a name="how-to-filter-reports-from-the-command-line"></a>如何：从命令行筛选报告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 从命令行的筛选器报表](https://docs.microsoft.com/visualstudio/profiling/how-to-filter-reports-from-the-command-line)。  
  
通过使用 VSPerfReport 命令选项，可以根据分析数据文件的特定时间段筛选报告，或将数据限制到一个或多个进程或线程。 有关此命令的详细信息，请参阅 [VSPerfReport](../profiling/vsperfreport.md)。  
  
|选项|描述|  
|-------------|-----------------|  
|**StartTime:**[*Value*]|仅显示此值（以毫秒为单位）之后收集的数据。|  
|**EndTime:**[*Value*]|仅显示此值（以毫秒为单位）之前收集的数据。|  
|**FilterFile:** `VSPFFile`|指定从“Visual Studio 性能报告”窗口生成的筛选器文件的位置。|  
|**MsFilter:**[*StartTime,Duration*]|仅显示从 `StartTime` 到 `Duration` 之间的数据（以毫秒为单位）。|  
|**Process:**[*Pid*]|仅显示来自指定进程的数据。|  
|**Thread:**[*ThreadID*]|仅显示来自指定线程的数据。|  
|**Thread:**[*ThreadID,ProcessID*]|仅显示与指定进程相关的指定线程的数据。|



