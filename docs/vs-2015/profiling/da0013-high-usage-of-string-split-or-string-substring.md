---
title: DA0013：String.Split 或 String.Substring 的使用率高 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.13
- vs.performance.rules.DAAvoidStringSubstr
- vs.performance.DA0013
- vs.performance.rules.DA0013
helpviewer_keywords:
- vs.performance.13
- vs.performance.rules.DA0013
ms.assetid: f501f423-bef9-4e08-bf96-c9ac9957e5a2
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c8f835e120f730f9c223477959e9c93dfefa240
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481494"
---
# <a name="da0013-high-usage-of-stringsplit-or-stringsubstring"></a>DA0013：String.Split 或 String.Substring 的使用率高
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[DA0013： 或 String.Substring 的使用率过高](https://docs.microsoft.com/visualstudio/profiling/da0013-high-usage-of-string-split-or-string-substring)。  
  
规则 Id |DA0013 |  
|类别 |。NET Framework 使用指南 |  
|分析方法 |采样 |  
|消息 |请考虑降低 String.Split 和 String.Substring 函数。 |  
|规则类型 |警告 |  
  
## <a name="cause"></a>原因  
 对 System.String.Split 或 System.String.Substring 方法的调用是分析数据的重要组成部分。 如果测试字符串中是否存在子字符串，请考虑使用 System.String.IndexOf 或 System.String.IndexOfAny。  
  
## <a name="rule-description"></a>规则说明  
 Split 方法对 String 对象执行操作，并返回包含原始子字符串的新字符串数组。 函数为返回的数组对象分配内存，并为其找到的每个数组元素分配一个新的 String 对象。 同样，Substr 方法对 String 对象执行操作，并返回与请求的子字符串等效的新字符串。  
  
 如果管理内存分配对于应用程序很重要，请考虑使用 String.Split 和 String.Substr 方法的替代方法。 例如，可以使用 IndexOf 或 IndexOfAny 方法查找 String 字符内的特定子字符串，而无需创建 String 类的新实例。  
  
## <a name="how-to-investigate-a-warning"></a>如何调查警告  
 双击“错误列表”窗口中的消息，导航到采样分析数据的[函数详细信息视图](../profiling/function-details-view.md)。 检查调用函数，以查找程序中使用 System.String.Split 或 System.String.Substr 方法最频繁的部分。 如果可能，请使用 IndexOf 或 IndexOfAny 方法查找 String 字符内的特定子字符串，而无需创建 String 类的新实例。



