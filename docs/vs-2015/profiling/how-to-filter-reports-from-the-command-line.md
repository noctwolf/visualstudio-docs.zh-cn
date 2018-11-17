---
title: 如何：从命令行筛选报告 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e9b140f-b44f-4a5c-bd65-d868ddc94023
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb8df34291d99d093ccf0d053d5dd1fbe2955232
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51789780"
---
# <a name="how-to-filter-reports-from-the-command-line"></a>如何：从命令行筛选报告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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



