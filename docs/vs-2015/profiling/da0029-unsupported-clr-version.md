---
title: DA0029：不支持的 CLR 版本 | Microsoft Docs
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
- vs.performance.29
- vs.performance.rules.DA0029
helpviewer_keywords:
- vs.performance.29
- vs.performance.DA0029
- vs.performance.rules.DA0029
ms.assetid: 76247259-c6f3-44c4-b3f9-d8dac16b5e0d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6334fc69607f6d39e75d20c3b3ca228507db169d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49265098"
---
# <a name="da0029-unsupported-clr-version"></a>DA0029：不支持的 CLR 版本
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

规则 Id |DA0029 |  
|类别 |分析工具使用情况 |  
|分析方法 |从命令行分析 |  
|消息 |在收集期间检测到不受支持的 CLR 版本。 托管的符号可能无法正确解析。 |  
|规则类型 |信息。 |  
  
## <a name="cause"></a>原因  
 尝试分析的应用程序使用的 [!INCLUDE[net_v11_long](../includes/net-v11-long-md.md)] 不受分析工具支持。  
  
## <a name="rule-description"></a>规则说明  
 出现此警告是因为，分析工具不能解析在应用程序中运行的托管代码符号。 分析工具无法解析运行 [!INCLUDE[net_v11_long](../includes/net-v11-long-md.md)] 的应用程序的托管代码符号。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 无。



