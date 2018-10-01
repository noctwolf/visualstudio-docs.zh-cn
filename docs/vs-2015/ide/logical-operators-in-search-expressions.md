---
title: 搜索表达式中的逻辑运算符 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Help Viewer 2.0, logical operators in search
- logical operators in search [Help Viewer 2.0]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0cf55bbdc025b4aabd13f7ded72c2ea69386a61b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470338"
---
# <a name="logical-operators-in-search-expressions"></a>搜索表达式中的逻辑运算符
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[搜索表达式中的逻辑运算符](https://docs.microsoft.com/visualstudio/ide/logical-operators-in-search-expressions)。  
  
通过使用逻辑运算符，可以在较简单的表达式基础上创建更复杂的搜索表达式，以改进内容的搜索。 如下表所示，逻辑运算符指定在搜索查询中组合多个搜索词的方式。  
  
> [!IMPORTANT]
>  必须使用全部大写字母的格式输入逻辑运算符，以便搜索引擎可以识别它们。  
  
|要搜索|使用|示例|结果|  
|-------------------|---------|-------------|------------|  
|同一主题中的两个词|AND|dib AND palette|包含“dib”和“palette”的主题。|  
|主题中的任一个词|或|raster OR vector|包含“raster”或“vector”的主题|  
|同一主题中包含第一个词，而不包含第二个词|NOT|"operating system" NOT DOS|包含“operating system”但不包含“DOS”的主题。|  
|主题中两个词相互靠近|相邻|user NEAR kernel|包含与“kernel”靠近的“user”的主题。|  
  
## <a name="see-also"></a>请参阅  
 [全文搜索提示](../ide/full-text-search-tips.md)   
 [查找信息](../ide/locate-information.md)



