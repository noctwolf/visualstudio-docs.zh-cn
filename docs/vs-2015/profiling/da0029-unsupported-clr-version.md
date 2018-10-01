---
title: DA0029：不支持的 CLR 版本 | Microsoft Docs
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
ms.openlocfilehash: df5deda533c21033d26af4b8dc08d98a5dafc583
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468560"
---
# <a name="da0029-unsupported-clr-version"></a>DA0029：不支持的 CLR 版本
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[DA0029： 不受支持的 CLR 版本](https://docs.microsoft.com/visualstudio/profiling/da0029-unsupported-clr-version)。  
  
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



