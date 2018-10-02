---
title: MSBuild 最佳做法 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: df388b4b5aeac30e5ee83e24dc08905507318f18
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477202"
---
# <a name="msbuild-best-practices"></a>MSBuild 最佳做法
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[MSBuild 最佳做法](https://docs.microsoft.com/visualstudio/msbuild/msbuild-best-practices)。  
  
  
我们建议下列编写 MSBuild 脚本的最佳做法：  
  
-   默认属性值的最佳处理方式是使用 `Condition` 特性，而不是声明可在命令行中重写其默认值的属性。 例如，使用  
  
     `<MyProperty Condition="$(MyProperty)" == ''>`  
  
     `MyDefaultValue`  
  
     `</MyProperty>`  
  
-   在选择项目时，请避免使用通配符。 而应显式指定文件。 这使得跟踪在添加或删除文件时可能出现的错误更加简单。  
  
## <a name="see-also"></a>请参阅  
 [高级概念](../msbuild/msbuild-advanced-concepts.md)



