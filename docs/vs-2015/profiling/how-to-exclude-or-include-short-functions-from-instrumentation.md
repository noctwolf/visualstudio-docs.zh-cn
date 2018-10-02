---
title: 如何：在检测中排除或包括短函数 | Microsoft Docs
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
- profiling tools, instrument events
- profiling tools, include short functions
- profiling tools, exclude short functions
ms.assetid: eaeead79-aafe-4490-86ff-6ed4cad9c15f
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f02e34e9fdb399aa8078342d3a8441f077a60f66
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484655"
---
# <a name="how-to-exclude-or-include-short-functions-from-instrumentation"></a>如何：在检测中排除或包括短函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 检测中包括短函数或排除](https://docs.microsoft.com/visualstudio/profiling/how-to-exclude-or-include-short-functions-from-instrumentation)。  
  
默认情况下，分析工具会从检测中排除*小型函数*。 小型函数是不执行任何函数调用的短函数。 排除这些小型函数会减少检测开销，从而提高检测速度。 排除小型函数还能减少性能分析数据文件 (.vsp) 的大小和分析所需的时间。 如果排除小型函数，花费在小型函数上的时间会减少，从而减少其父函数的独占和非独占时间。 可以在检测中排除或包括小型函数，具体在以下过程中说明。  
  
### <a name="to-exclude-or-include-short-functions-from-instrumentation"></a>在检测中排除或包括短函数  
  
1.  在“性能资源管理器”中，选择“性能会话”，然后右键单击并选择“属性”。  
  
     随即显示“属性页”对话框。  
  
2.  在“属性页”中，单击“检测”属性。  
  
3.  若要从检测中排除短函数，请选择“从检测中排除短函数”。 此为默认设置。  
  
     或  
  
     若要在检测中包括短函数，请清除“从检测中排除短函数”。  
  
4.  单击 **“确定”**。  
  
## <a name="see-also"></a>请参阅  
 [控制数据收集](../profiling/controlling-data-collection.md)   
 [性能会话属性](../profiling/performance-session-properties.md)



