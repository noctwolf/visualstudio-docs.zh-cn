---
title: MSBuild 最佳做法 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- best practices, MSBuild
- MSBuild, best practices
ms.assetid: 90ef8693-e921-410a-a377-fe4d13f58c48
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 622d7b087e94d21f86691b88c3af4891aa533e9a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013205"
---
# <a name="msbuild-best-practices"></a>MSBuild 最佳做法
我们建议下列编写 MSBuild 脚本的最佳做法：  
  
-   默认属性值的最佳处理方式是使用 `Condition` 特性，而不是声明可在命令行中重写其默认值的属性。 例如，使用  
  
```xml
<MyProperty Condition="'$(MyProperty)' == ''">
   MyDefaultValue
</MyProperty>
```
  
-   在选择项目时，请避免使用通配符。 而应显式指定文件。 这使得跟踪在添加或删除文件时可能出现的错误更加简单。  
  
## <a name="see-also"></a>请参阅  
 [高级概念](../msbuild/msbuild-advanced-concepts.md)
