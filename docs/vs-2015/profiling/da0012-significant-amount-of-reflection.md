---
title: DA0012：大量反射 | Microsoft Docs
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
- vs.performance.rules.DAReflection
- vs.performance.12
- vs.performance.rules.DA0012
- vs.performance.DA0011
ms.assetid: c92a1d76-21fa-426e-8b1b-a3c08e9bcbca
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 458f1bc74d8660e640139bff2f379a66eafa2919
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476581"
---
# <a name="da0012-significant-amount-of-reflection"></a>DA0012：大量反射
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[DA0012： 大量反射](https://docs.microsoft.com/visualstudio/profiling/da0012-significant-amount-of-reflection)。  
  
规则 Id |DA0012 |  
|类别 |。NET Framework 使用情况 |  
|分析方法 |采样 |  
|消息 |你可能存在过度反射。 它是代价高昂的操作。 |  
|规则类型 |警告 |  
  
## <a name="cause"></a>原因  
 对 System.Reflection 方法（如 InvokeMember 和 GetMember）或 Type 方法（如 MemberInvoke）的调用是分析数据的重要组成部分。 如果可能，请考虑用对依赖程序集方法的早期绑定来替代这些方法。  
  
## <a name="rule-description"></a>规则说明  
 反射是 .NET framework 的一项灵活功能，可用于将应用程序后期绑定到依赖的运行时程序集，或在运行时期间创建并动态执行新类型。 但是，频繁使用或紧凑循环地调用这些技术则可导致性能降低。  
  
 有关详细信息，请参阅 MSDN 上 Microsoft 模式和做法库“提高 .NET 应用程序性能和可扩展性”卷中“第 5 章 - 提高托管代码性能”的 [Reflection and Late Binding](http://go.microsoft.com/fwlink/?LinkId=177826)（反射和后期绑定）部分。  
  
## <a name="how-to-investigate-a-warning"></a>如何调查警告  
 双击“错误列表”窗口中的消息，导航到分析数据的[函数详细信息视图](../profiling/function-details-view.md)。 检查 System.Type 或 System.Reflection 方法的调用函数，以查找程序中使用 .NET Reflection API 最频繁的部分。 避免使用返回元数据的方法。 当应用程序的性能十分重要时，可能需要避免在运行时使用后期绑定或动态创建类型。



